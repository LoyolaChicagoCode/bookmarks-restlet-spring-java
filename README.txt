API documentation

Whenever a "-u username" command-line argument is present,
you will be prompted for the password.

User

  create

  curl -X PUT -d 'user[email]=laufer@cs.luc.edu' \
  -d 'user[full_name]=Konstantin' -d 'user[password]=pass' \
  http://localhost:3000/bookmarks-restlet-spring/users/klaufer

  read ("-X GET" is optional)

  curl -X GET http://localhost:3000/bookmarks-restlet-spring/users/klaufer

  update

  curl -u klaufer -X PUT -d 'user[email]=laufer@cs.luc.edu' \
  -d 'user[full_name]=Konstantin Laufer' -d 'user[password]=pass' \
  http://localhost:3000/bookmarks-restlet-spring/users/klaufer

  delete

  curl -u klaufer -X DELETE \
  http://localhost:3000/bookmarks-restlet-spring/users/klaufer

Bookmarks

  read (trailing slash required!)

  curl http://localhost:3000/bookmarks-restlet-spring/users/klaufer/bookmarks/

Bookmark

  create/update

  curl -u klaufer -X PUT -d 'bookmark[short_description]=Loyola' \
  -d 'bookmark[long_description]=Loyola home page' -d 'bookmark[restrict]=false' \
  http://localhost:3000/bookmarks-restlet-spring/users/klaufer/bookmarks/http://www.luc.edu/

  read (authentication required for private bookmarks where bookmark[restrict]=true)

  curl \
  http://localhost:3000/bookmarks-restlet-spring/users/klaufer/bookmarks/http://www.luc.edu/

  delete

  curl -u klaufer -X DELETE \
  http://localhost:3000/bookmarks-restlet-spring/users/klaufer/bookmarks/http://www.luc.edu/
