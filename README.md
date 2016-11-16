# nest-userdb
basic user database with hierarchical roles assignment

Roles can be nested hierarchically. Thus single rights may be aggregated to right groups and to roles. Roles my be assigned to users.

View `V_USER_ROLES` resolves the hierarchy to a flat representation of all users to her roles. This View may be used for Tomcat's [JDBCRealm](https://tomcat.apache.org/tomcat-9.0-doc/realm-howto.html#JDBCRealm):


        <Realm className="org.apache.catalina.realm.JDBCRealm"
					driverName="my.favorite.Driver"
					connectionURL="jdbc:favorite/database"
					userTable="user" userNameCol="user_name" userCredCol="password"
					userRoleTable="v_user_role" roleNameCol="role_name" />
