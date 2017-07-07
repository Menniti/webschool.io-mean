# MongoDb - Projeto Final
**Autor:** Luiz Menniti
**Data** Date.now() //em timestamp

## Para qual sistema você usaria o MongoDB (diferente desse)?
    
## Qual a modelagem da sua coleção de `users`?
    > user
{
        "name" : "Luiz",
        "type_member" : "Master",
        "dateRegister" : "14/08/2802",
        "avatarPath" : "http://lanaesquina.com",
        "auth" : [
                {
                        "username" : "userluiz",
                        "email" : "luiz.menniti@gmail.com",
                        "password" : "aeae",
                        "lastAccess" : "ontem",
                        "online" : "True",
                        "disable" : "False",
                        "hashToken" : "9123h9u1bsu7h7haojh7s7"
                }
        ]
}    
## Qual a modelagem da sua coleção de `projects`?
    > project
{
        "_id" : ObjectId("5830f80de5839e2bd59ca625"),
        "name" : "Project 3",
        "description" : "Project 2 Description",
        "date_begin" : 0.0010075566750629723,
        "date_dream" : 0.0010224948875255625,
        "date_end" : 0.000925925925925926,
        "visible" : true,
        "realocate" : "No",
        "expired" : 0.000925925925925926,
        "visializable_mod" : true,
        "tags" : [
                "Luiz2",
                "project2",
                "tag2"
        ],
        "members" : [
                {
                        "type_member" : "Master",
                        "user_id" : "2"
                }
        ],
        "goals" : [
                {
                        "name" : "Instagram2",
                        "description" : "Construir instagram BE MEAN!2",
                        "date_begin" : 0.0007518796992481203,
                        "date_dream" : 0.0007518796992481203,
                        "date_end" : 0.0007518796992481203,
                        "realocate" : "No",
                        "expired" : 0.000925925925925926,
                        "tags" : [
                                "Tag_goal",
                                "Win"
                        ],
                        "activities" : [
                                {
                                        "name" : "Activitie_Project 2",
                                        "description" : "Aprender MEAN2",
                                        "date_begin" : 0.000847457627118644,
                                        "date_dream" : 0.000847457627118644,
                                        "date_end" : 0.0009389671361502347,
                                        "realocate" : "Yes",
                                        "expired" : 0.000925925925925926,
                                        "tags" : [
                                                "tag_activies",
                                                "activity 2"
                                        ],
                                        "comments" : [
                                                {
                                                        "text" : "Ajudar os amigos do role2",
                                                        "date_comment" : 0.000925925925925926,
                                                        "members" : [
                                                                "Luiz",
                                                                "hoho"
                                                        ],
                                                        "files" : [
                                                                {
                                                                        "path" : "//ronaldo",
                                                                        "weight" : "hoho",
                                                                        "name" : "Hoho_file"
                                                                }
                                                        ]
                                                }
                                        ],
                                        "historics" : [ ]
                                }
                        ]
                }
        ]
}
## Create - cadastro

```
 1. Cadastre 10 Usuarios diferentes.
    { "_id" : ObjectId("584d9017a1a03ce675b9b1f8"), "name" : "Luiz", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userluiz", "email" : "luiz.menniti@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d904ca1a03ce675b9b1f9"), "name" : "Rafael", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userrafael", "email" : "rafael@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9d54a1a03ce675b9b1fa"), "name" : "Rafael", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userrafael", "email" : "rafael@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9d62a1a03ce675b9b1fb"), "name" : "Luciano", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userluciano", "email" : "luciano@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9d88a1a03ce675b9b1fc"), "name" : "Ronaldo", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userRonaldo", "email" : "Ronaldoo@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9dc0a1a03ce675b9b1fd"), "name" : "Romario", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userRomario", "email" : "Romario@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9deca1a03ce675b9b1fe"), "name" : "Rafaela", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userRafaela", "email" : "Rafaela@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9e71a1a03ce675b9b1ff"), "name" : "Rafaela", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userRafaela", "email" : "Rafaela@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9e98a1a03ce675b9b200"), "name" : "Fernanda", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userFernanda", "email" : "Fernanda@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9ec0a1a03ce675b9b201"), "name" : "Luiza", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userLuiza", "email" : "luiza@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9f84a1a03ce675b9b202"), "name" : "Natalia", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "usernatalia", "email" : "natalia@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
    { "_id" : ObjectId("584d9fefa1a03ce675b9b203"), "name" : "Joana", "type_member" : "Master", "dateRegister" : "14/08/2802", "avatarPath" : "http://lanaesquina.com", "auth" : [ { "username" : "userjoana", "email" : "joana@gmail.com", "password" : "aeae", "lastAccess" : "ontem", "online" : "True", "disable" : "False", "hashToken" : "9123h9u1bsu7h7haojh7s7" } ] }
 2. Cadastre 5 projectos diferentes.
    { "_id" : ObjectId("584db6c5a1a03ce675b9b204"), "name" : "Project 1", "description" : "Project 1 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "win" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Luiza" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Romario" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal1", "tag_goal2", "tag_goal3" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
    { "_id" : ObjectId("584db72ea1a03ce675b9b205"), "name" : "Project 2", "description" : "Project 2 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "win" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Fernanda" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Romario" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal4", "tag_goal5", "tag_goal6", "tag_goal1" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
    { "_id" : ObjectId("584db840a1a03ce675b9b206"), "name" : "Project 3", "description" : "Project 3 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "power" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Fernanda" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Romario" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal7", "tag_goal8", "tag_goal9", "tag_goal6" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
    { "_id" : ObjectId("584db9dba1a03ce675b9b209"), "name" : "Project 5", "description" : "Project 5 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "power" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Natalia" }, { "type_member" : "Master", "name" : "Rafaela" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Luciano" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal13", "tag_goal14", "tag_goal15", "tag_goal6" ] } ] }
    { "_id" : ObjectId("584db8bfa1a03ce675b9b207"), "name" : "Project 3", "description" : "Project 3 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "power" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Natalia" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Luciano" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal10", "tag_goal11", "tag_goal12", "tag_goal6" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
    { "_id" : ObjectId("584db94ba1a03ce675b9b208"), "name" : "Project 4", "description" : "Project 4 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "power" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Rafaela" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Luciano" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal10", "tag_goal11", "tag_goal12", "tag_goal6" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
``` 
## Retrieve - busca
```
 1.Liste as informações dos membros de 1 projeto específico que deve ser buscado pelo seu nome de forma a não ligar para maiúsculas e minúsculas.
 db.projects.find({name: /prOject 1/i})
    { "_id" : ObjectId("584db6c5a1a03ce675b9b204"), "name" : "Project 1", "description" : "Project 1 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "win" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Luiza" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Romario" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal1", "tag_goal2", "tag_goal3" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }

 2.Liste todos os projetos com a tag que você escolheu para os 3 projetos em comum.
  db.projects.find({tags: /power/i})
    { "_id" : ObjectId("584db840a1a03ce675b9b206"), "name" : "Project 3", "description" : "Project 3 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "power" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Fernanda" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Romario" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal7", "tag_goal8", "tag_goal9", "tag_goal6" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
    { "_id" : ObjectId("584db9dba1a03ce675b9b209"), "name" : "Project 5", "description" : "Project 5 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "power" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Natalia" }, { "type_member" : "Master", "name" : "Rafaela" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Luciano" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal13", "tag_goal14", "tag_goal15", "tag_goal6" ] } ] }
    { "_id" : ObjectId("584db8bfa1a03ce675b9b207"), "name" : "Project 3", "description" : "Project 3 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "power" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Natalia" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Luciano" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal10", "tag_goal11", "tag_goal12", "tag_goal6" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
    { "_id" : ObjectId("584db94ba1a03ce675b9b208"), "name" : "Project 4", "description" : "Project 4 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "power" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Rafaela" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Luciano" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal10", "tag_goal11", "tag_goal12", "tag_goal6" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
 
 3.Liste apenas os nomes de todas as atividades para todos os projetos.
   db.projects.find({}, {"goals.activities.name":1 })
    { "goals" : [ { "activities" : [ { "name" : "proj_Activitie1" }, { "name" : "proj_Activitie2" } ] } ] }
    { "goals" : [ { "activities" : [ { "name" : "proj_Activitie1" }, { "name" : "proj_Activitie2" } ] } ] }
    { "goals" : [ { "activities" : [ { "name" : "proj_Activitie1" }, { "name" : "proj_Activitie2" } ] } ] }
    { "goals" : [ {  } ] }
    { "goals" : [ { "activities" : [ { "name" : "proj_Activitie1" }, { "name" : "proj_Activitie2" } ] } ] }
    { "goals" : [ { "activities" : [ { "name" : "proj_Activitie1" }, { "name" : "proj_Activitie2" } ] } ] }
    
 4.Liste todos os projetos que não possuam uma tag.
    db.projects.find({ tags: { $ne:'power'}} ) 
    { "_id" : ObjectId("584db6c5a1a03ce675b9b204"), "name" : "Project 1", "description" : "Project 1 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "win" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Luiza" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Romario" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal1", "tag_goal2", "tag_goal3" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
    { "_id" : ObjectId("584db72ea1a03ce675b9b205"), "name" : "Project 2", "description" : "Project 2 Description", "date_begin" : 0.0010075566750629723, "date_dream" : 0.0010224948875255625, "date_end" : 0.000925925925925926, "visible" : true, "realocate" : "No", "expired" : 0.000925925925925926, "visializable_mod" : true, "tags" : [ "project1_tag1", "project1_tag2", "project1_tag3", "win" ], "members" : [ { "type_member" : "Master", "name" : "Joana" }, { "type_member" : "Master", "name" : "Luiz" }, { "type_member" : "Master", "name" : "Fernanda" }, { "type_member" : "Master", "name" : "Ronaldo" }, { "type_member" : "Master", "name" : "Romario" } ], "goals" : [ { "name" : "Instagram2", "description" : "Construir instagram BE MEAN!2", "date_begin" : 0.0007518796992481203, "date_dream" : 0.0007518796992481203, "date_end" : 0.0007518796992481203, "realocate" : "No", "expired" : 0.000925925925925926, "tags" : [ "tag_goal4", "tag_goal5", "tag_goal6", "tag_goal1" ], "activities" : [ { "name" : "proj_Activitie1", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] }, { "name" : "proj_Activitie2", "description" : "Aprender MEAN2", "date_begin" : 0.000847457627118644, "date_dream" : 0.000847457627118644, "date_end" : 0.0009389671361502347, "realocate" : "Yes", "expired" : 0.000925925925925926, "tags" : [ "tag_activies", "activity 2" ], "comments" : [ { "text" : "Ajudar os amigos do role2", "date_comment" : 0.000925925925925926, "members" : [ "Luiz", "hoho" ], "files" : [ { "path" : "//ronaldo", "weight" : "hoho", "name" : "Hoho_file" } ] } ], "historics" : [ ] } ] } ] }
    
 5.Liste todos os usuários que não fazem parte do primeiro projeto cadastrado.
    
    var arr_list = []
    var name_user = db.projects.findOne({ name: /project 1/i }, {"members.name":1})
    function logArrayElements(element, index, array){arr_list.push(element['name']);}
    name_user.members.forEach(logArrayElements);
    arr_list = [ "Joana", "Luiz", "Luiza", "Ronaldo", "Romario" ]
    
    db.users.find({name: {$nin:arr_list}}, {_id:0,name:1})
        { "name" : "Rafael" }
        { "name" : "Rafael" }
        { "name" : "Luciano" }
        { "name" : "Rafaela" }
        { "name" : "Rafaela" }
        { "name" : "Fernanda" }
        { "name" : "Natalia" }
    
    
``` 
## Update - alteração

## Delete - remoção
        
## Sharding
// coloque aqui todos os comandos que você executou

## Replica
// coloque aqui todos os comandos que você executou