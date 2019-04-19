1. Download the project zip file ( https://github.com/francis-han/IRS-RS-2019-03-09-IS1PT-GRP-Pepper-PatientMatchingSystem/SystemCodes/KIE/PHQTimeTable.zip ) . It is best run with JBPM 7.16 . The link is /Miscellaneous/LINK_yo_JBPM7_16.

2. In KIE workbench, create a space “PHQTimeTable”. Import the project. Deploy the project.

3. Sending API command to setup solver and also sending the input system. Finally retrieve the result. To send POSTMAN command, follow the following steps:

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

    The process will be triggered and finished around 3-5 minutes.

    Part 3 (or use GET command in POSTMAN)

    goto any browser in vm

    goto http://localhost:8080/kie-server/services/rest/server/containers/PHQTimeTable_1.0.0/solvers/TimeSolver/bestsolution

    log in as wbadmin if ask for identity
