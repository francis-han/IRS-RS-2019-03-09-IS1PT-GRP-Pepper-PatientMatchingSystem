This folder contains the KIE related files.

1. Follow the user manual. Create space and import the zip file into KIE workbench.
2. To send POSTMAN command, follow the following steps:

    Part 1

    >command
    PUT

    >address
    http://localhost:8080/kie-server/services/rest/server/containers/PHQTimeTable_1.0.0/solvers/TimeSolver

    >authorization
    choose basic auth or basic authentication under "Authorization"
    use wbadmin as user and password

    >headers

    authorization: Basic cGxhbm5lcjpQbGFubmVyMTIzXw==
    X-KIE-ContentType: xstream
    content-type: application/xml

    >Body

    <solver-instance>
    <solver-config-file>com/phqtime/phqtimetable/TimeSolver.solver.xml</solver-config-file>
    </solver-instance>

    Part 2
    
    >Command
    POST

    >authorization
    choose basic auth or basic authentication under "Authorization"
    use wbadmin as user and password


    >headers

    authorization: Basic cGxhbm5lcjpQbGFubmVyMTIzXw==
    X-KIE-ContentType: xstream
    content-type: application/xml

    >Body
    Use the content of postman_POST_body.txt in this folder
    
    Part 3 (or use GET command in POSTMAN)

    goto any browser in vm

    goto http://localhost:8080/kie-server/services/rest/server/containers/PHQTimeTable_1.0.0/solvers/TimeSolver/bestsolution

    log in as wbadmin if ask for identity
