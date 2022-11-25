# graphiz-sample

![BasicDiagram](https://dreampuf.github.io/GraphvizOnline/#digraph%20microservices%7B%0Arankdir%3DLR%3B%20%0Acompound%3Dtrue%3B%0Anode%5Bshape%3Drectangle%5D%0Asubgraph%20cluster_clientside%7B%0A%20%20%20%20%7Brank%3Dsame%20mobile_apps%20webapp%20%7D%0A%20%20%20%20mobile_apps%2C%20webapp%3B%0A%7D%0Asubgraph%20cluster_aws%20%7B%0A%20%20%20%20bgcolor%3Dlightgrey%3B%0A%20%20%20%20node%5Bcolor%3Dorange%5D%0A%20%20%20%20label%20%3D%20%22aws%5Clap-southeast-1%22%3B%0A%20%20%20%20labeljust%3D%22r%22%20%20%20%0A%0A%20%20%20%20subgraph%20cluster_vpc%20%7B%0A%20%20%20%20%20%20bgcolor%3Dwhite%3B%0A%20%20%20%20%20%20label%20%3D%20%22vpc%22%3B%0A%20%20%20%20subgraph%20cluster_lb%20%7B%0A%20%20%20%20%20%20%20%20bgcolor%3Dlightblue%3B%0A%20%20%20%20%20%20%20%20style%3Ddashed%3B%0A%20%20%20%20%20%20label%20%3D%20%22Public%20subnet%22%3B%0A%20%20%20%20%20%20lb%3B%0A%20%20%20%20%7D%0A%20%20%20%20subgraph%20cluster_gc_1%20%7B%0A%20%20%20%20%20%20%20%20style%3Ddashed%3B%0A%20%20%20%20%20%20%20%20bgcolor%3Dlightblue%3B%0A%20%20%20%20%20%20%20%20%7Brank%3Dsame%20orders%20products%20cart%20checkout%20%7D%0A%20%20%20%20%20%20%20%20label%20%3D%20%22Private%20subnet%22%3B%0A%20%20%20%20%20%20%20%20orders%2C%20products%2C%20cart%2C%20checkout%20%5Bshape%3Dhexagon%2C%20fixedsize%3Dtrue%2C%20width%3D1%2C%20height%3D1%5D%0A%20%20%20%20%20%20%20%20RDS_DB%20%5Bshape%3Dcylinder%5D%0A%20%20%20%20%7D%0A%20%20%20%20%7D%0A%20%20%7D%0A%2F%2F%7Bmobile_apps%2C%20webapp%7D%20-%3E%20lb%20%0Awebapp%20-%3E%20lb%20%5Blhead%3Dcluster_lb%5D%3B%0Alb%20-%3E%20orders%3As%2C%20products%3Aw%2C%20cart%3Aw%2C%20checkout%3An%0Aorders%2C%20products%2C%20checkout%20-%3E%20RDS_DB%3B%0Acart-%3E%20checkout%0A%7D%0A)


![Alt text](https://g.gravizo.com/svg?
  digraph G {
    size ="4,4";
    main [shape=box];
    main -> parse [weight=8];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf}
    init -> make_string;
    edge [color=red];
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
)
