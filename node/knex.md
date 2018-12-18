# Get started with node and knex

## Setup project

Install knex: `npm install -g knex`

Create project:
```
mkdir cnode && cnode
yarn init -y
yarn add knex mysql2 objection
```

Create file config with knex:
```
knex init
```

Update `knexfile.js`
```
module.exports = {
  development: {
    client: 'mysql2',
    connection: {
      host: '127.0.0.1',
      user: 'root',
      password: '',
      database: 'cnode'
    }
  }
  ...
 };
```

Create migrations:
```
knex migrate:make create_ideas
knex migrate:make create_comments
```

Edit file `create_ideas.js` in migrations:

```
exports.up = function(knex) {
  return knex.schema.createTable('ideas', table => {
    table.increments('id').primary();
    table.string('idea');
    table.string('creator');
  });
};

exports.down = function(knex) {
  return knex.schema.dropTable('ideas');
};
```

Edit file `create_comments.js` in migrations:
```
exports.up = function(knex) {
  return knex.schema.createTable('comments', table => {
    table.increments('id').primary();
    table.string('comment');
    table.string('creator');
    table
      .integer('ideas_id')
      .unsigned()
      .references('ideas.id');
  });
};

exports.down = function(knex) {
  return knex.schema.dropTable('comments');
};
```

Finally, I ran the migrations using the command:
```
knex migrate:latest
```

Optionally for rolls back the latest migration group using command:
```
knex migrate:rollback
```

## Database Seeding

Generate a seed for populate data for database:
```
knex seed:make ideas
```
Edit file `seeds/idea.js`:
```
exports.seed = function(knex, Promise) {
  // Deletes ALL existing entries
  return knex('ideas')
    .del()
    .then(function() {
      // Inserts seed entries
      return knex('ideas').insert([
        { creator: 'Ali', idea: 'A To Do list app!' },
        { creator: 'Ali', idea: 'Create blog' },
        { creator: 'Ali', idea: 'Change the world' }
      ]);
    });
};
```

Run seed with this command => `knex seed:run`

## Models

Create file `models\schema.js`
```
const Knex = require('knex');
const connection = require('../knexfile');
const { Model } = require('objection');

const knexConnection = Knex(connection['development']);

Model.knex(knexConnection);

class Comment extends Model {
  static get tableName() {
    return 'comments';
  }

  static get relationMappings() {
    return {
      idea: {
        relation: Model.BelongsToOneRelation,
        modelClass: Idea,
        join: {
          from: 'comments.ideas_id',
          to: 'ideas.id'
        }
      }
    };
  }
}

class Idea extends Model {
  static get tableName() {
    return 'ideas';
  }

  static get relationMappings() {
    return {
      comments: {
        relation: Model.HasManyRelation,
        modelClass: Comment,
        join: {
          from: 'ideas.id',
          to: 'comments.ideas_id'
        }
      }
    };
  }
}

module.exports = { Idea, Comment };

```

