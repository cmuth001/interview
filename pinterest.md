// HTTP
// - GET/POST/DELETE/PUT
//   - query paramters // GET
//   - payload // POST

// - headers

// - verb - type of request
// - url
// - parameter
// - body/payload

// | Pattern                      | Endpoint name            |
// |------------------------------|--------------------------|
// | GET /users                   | get_all_users            |
// | GET /users/<ID>              | get_user                 |
// | GET /users/<ID>/preferences  | get_user_preferences     |
// | GET /users/<ID>/<ID>         | get_user_posts_in_thread |
// | GET /thread/<ID>             | get_thread               |
// | GET /thread/<IGET /usersD>/comments    | get_thread_comments      |
// | GET /thread/<ID>/likes       | get_thread_likes         |
// | POST /thread                 | create_thread            |
// | DELETE /comments/<ID>        | delete_comment           |
// | ...                          | ...                      |

// input: request
// put: endpoint name

// | Input: String                                   | Expected output      |
// |-------------------------------------------------|----------------------|
// | GET /users                                      | get_all_users        |
// | GET /users/abc123                               | get_user             |
// | GET /users/def456                               | get_user             |
// | GET /users/thisuseridlookslikewords/preferences | get_user_preferences |
// | GET /thread/thisthreadidlookslikewords/comments | get_thread_comments  |
// | ...                                             | ...                  |
