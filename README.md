de importação de arranha-céus *
de highrise.models importar *
de asyncio importar executar como arun
do frasco importar frasco
de threading importar Thread
de highrise.__main__ importar *
de emotes importar*
importar aleatório
importar asyncio
tempo de importação

classe Bot(BaseBot):
    def __init__(próprio):
        super().__init__()
        self.emote_looping = Falso
        self.user_emote_loops = {}
        self.loop_task = Nenhum
        self.is_teleporting_dict = {}
        self.following_user = Nenhum
        self.following_user_id = Nenhum
        self.kus = {}
        self.posições_do_usuário = {}
        self.posição_tarefas = {}
        
    haricler = ["c1q","_5q"]

    async def on_emote(self, user: Usuário, emote_id: str, receiver: Usuário | Nenhum) -> Nenhum:
      print(f"{user.username} emocionado: {emote_id}")
  
    async def on_start(self, session_metadata: SessionMetadata) -> Nenhum:
        print("oi, estou vivo?")
        aguarde self.highrise.tg.create_task(self.highrise.teleport(
            session_metadata.user_id, Posição( 13,00, 1,00, 5,00, "FrontRight")))
             

    async def on_user_join(self, usuário: Usuário, posição: Posição | AnchorPosition) -> Nenhum:
        await self.highrise.chat(f" Bem vindoðŸ– ï¸ sinta-se a vontade dono @DjLobin @{user.username} Emotes 0 - 96 ")
        tentar:
            emote_name = random.choice(lista(secili_emote.keys()))
            emote_info = secili_emote[nome_emote]
            emote_a_enviar = emote_info["valor"]
            aguarde self.send_emote(emote_para_enviar, user.id)
        exceto Exceção como e:
            print(f"Erro ao enviar emote para o usuário {user.id}: {e}")
  
    async def on_user_leave(self, usuário: Usuário):
    
        user_id = usuário.id
        farewell_message = f" volte logo ðŸ˜®â€ ðŸ'¨ðŸ'•! @{user.username}"
        se user_id em self.user_emote_loops:
            aguarde self.stop_emote_loop(user_id)
        aguarde self.highrise.chat(mensagem_de_despedida)
  

    async def on_chat(self, user: Usuário, mensagem: str) -> Nenhum:
        """Em um bate-papo recebido em toda a sala."""    

        se mensagem.lower().startswith("Ä "):
          aguarde self.highrise.send_emote("emote-kiss")

        isimler1 = [
            "\n1 - @",
            "\n2 - @",
            "\n3 - @",
            "\n4 - @",
            "\n5 - @",
        ]
        isimler2 = [
            "\n6 - @",
            "\n7 - @",
            "\n8 - @",
            "\n9 - @",
            "\n10 - @",
        ]
        isimler3 = [
            "\n11 - @",
            "\n12 - @",
            "\n13 - @",
            "\n14 - @",
            "\n15 - @",
        ]
        isimler4 = [
            "\n16 - @",
            "\n17 - @",
            "\n18 - @",
            "\n19 - @",
            "\n20 - @",
        ]
        isimler5 = [
            "\n21 - @",
            "\n22 - @",
            "\n23 - @",
            "\n24 - @",
            "\n25 - @",
            "\n26 - @"

            # DiÄŸer isimler buraya eklenecek
        ]

        
        se mensagem.lower().startswith("Ä "):
          aguarde self.highrise.chat("\n".join(isimler1))
          aguarde self.highrise.chat("\n".join(isimler2))
          aguarde self.highrise.chat("\n".join(isimler3))
          aguarde self.highrise.chat("\n".join(isimler4))
          aguarde self.highrise.chat("\n".join(isimler5))
          aguarde self.highrise.chat(f"\n\nÃ–nerileriniz için")

          


        mensagem = mensagem.lower()

        localizações_de_teletransporte = {
            "vip1": Posição(3,00, 0,00, 0,00),
            "vip2": Posição(13.5, 11.0, 7.5),
            "vip3": Posição(11., 1., 11.),
            "deneme1": Posição(random.randint(0, 40), random.randint(0, 40), random.randint(0, 40)),
            "deneme1": Posição(random.randint(0, 40), random.randint(0, 40), random.randint(0, 40))
        }

        para location_name, posição em teleport_locations.items():
            se mensagem ==(nome_do_local):
                tentar:
                    aguarde self.teleport(usuário, posição)
                exceto:
                    print("Ocorreu um erro durante o teletransporte")
                  
        se message.lower().startswith("ina") e aguarde self.is_user_allowed(usuário):
            target_username = mensagem.split("@")[-1].strip()
            room_users = aguardar self.highrise.get_room_users()
            user_info = next((info para informações em room_users.content se info[0].username.lower() == target_username.lower()), Nenhum)

            se user_info:
                target_user_obj, posição_inicial = info_do_usuário
                tarefa = asyncio.create_task(self.reset_target_position(obj_usuário_alvo, posição_inicial))

                se target_user_obj.id não estiver em self.position_tasks:
                    self.position_tasks[objeto_usuário_alvo.id] = []
                self.position_tasks[obj.id_usuário_alvo].append(tarefa)

        elif message.lower().startswith("ina") e aguarde self.is_user_allowed(usuário):
            target_username = mensagem.split("@")[-1].strip()
            room_users = aguardar self.highrise.get_room_users()
            target_user_obj = next((user_obj para user_obj, _ em room_users.content se user_obj.username.lower() == target_username.lower()), Nenhum)

            se target_user_obj:
                tarefas = self.position_tasks.pop(objeto_usuário_alvo.id, [])
                para tarefa em tarefas:
                    tarefa.cancelar()
                print(f"Interrompendo o loop de monitoramento de posição para {target_username}")
            outro:
                print(f"Usuário {target_username} não encontrado na sala.")

        se mensagem.lower().startswith("info"):
            target_username = mensagem.split("@")[-1].strip()
            aguarde self.userinfo(usuário, nome_de_usuário_alvo)


        se message.startswith("+x") ou message.startswith("-x"):
            aguarde self.adjust_position(usuário, mensagem, 'x')
        mensagem elif.startswith("+y") ou mensagem.startswith("-y"):
            aguarde self.adjust_position(usuário, mensagem, 'y')
        mensagem elif.startswith("+z") ou mensagem.startswith("-z"):
            aguarde self.adjust_position(usuário, mensagem, 'z')
              
      
        allowed_commands = ["switch", "degis", "deÄŸiÅŸ","deÄŸis","degiÅŸ"]
        se houver algum (message.lower().startswith(command) para comando em allowed_commands) e aguarde self.is_user_allowed(user):
            target_username = mensagem.split("@")[-1].strip()

        
            se target_username não estiver em self.haricler:
                aguarde self.switch_users(usuário, nome_de_usuário_alvo)
            outro:
                print(f"{target_username} está na lista de exclusão e não será afetado pela troca.")

        se message.lower().startswith("Tp") ou message.lower().startswith("tp"):
          target_username = mensagem.split("@")[-1].strip()
          aguarde self.teleport_to_user(usuário, nome_de_usuário_alvo)
        se aguardar self.is_user_allowed(usuário) e message.lower().startswith("T"):
            target_username = mensagem.split("@")[-1].strip()
            se target_username não estiver em self.haricler:
                aguarde self.teleport_user_next_to(nome_de_usuário_de_destino, usuário)
        se message.lower().startswith("--") e aguarde self.is_user_allowed(usuário):
            partes = mensagem.split()
            se len(partes) == 2 e parts[1].startswith("@"):
                target_username = partes[1][1:]
                target_user = Nenhum

                room_users = (aguarde self.highrise.get_room_users()).content
                para room_user, _ em room_users:
                    se room_user.username.lower() == target_username e room_user.username.lower() não estiverem em self.haricler:
                        target_user = usuário_da_sala
                        quebrar

                se target_user:
                    tentar:
                        kl = Posição(random.randint(0, 40), random.randint(0, 40), random.randint(0, 40))
                        aguarde self.teleport(target_user, kl)
                    exceto Exceção como e:
                        print(f"Ocorreu um erro durante o teletransporte: {e}")
                outro:
                    print(f"O nome do usuário alvo é '{target_username}' e o nome do usuário alvo é ')."

        se message.lower() == "rtp completo" ou message.lower() == "kaÃ§ completo":
            se user.id não estiver em self.kus:
                self.kus[user.id] = Falso

            se não self.kus[user.id]:
                self.kus[user.id] = Verdadeiro

                tentar:
                    enquanto self.kus.get(user.id, False):
                        kl = Posição(random.randint(0, 29), random.randint(0, 29), random.randint(0, 29))
                        aguarde self.teleport(usuário, kl)

                        aguarde asyncio.sleep(0.7)
                exceto Exceção como e:
                    print(f"Teleport sÄ±rasÄ±nda bir hata oluÅŸtu: {e}")

        se message.lower() == "dur" ou message.lower() == "stop":
            se user.id em self.kus:
                self.kus[user.id] = Falso

        se message.lower().startswith("ina") e aguarde self.is_user_allowed(usuário):
            target_username = mensagem.split("@")[-1].strip().lower()

            se target_username não estiver em self.haricler:
                room_users = (aguarde self.highrise.get_room_users()).content
                target_user = next((u para u, _ em room_users se u.username.lower() == target_username), Nenhum)

                se target_user:
                    se target_user.id não estiver em self.is_teleporting_dict:
                        self.is_teleporting_dict[target_user.id] = Verdadeiro

                        tentar:
                            enquanto self.is_teleporting_dict.get(target_user.id, False):
                                kl = Posição(random.randint(0, 39), random.randint(0, 29), random.randint(0, 39))
                                aguarde self.teleport(target_user, kl)
                                aguarde asyncio.sleep(1)
                        exceto Exceção como e:
                            print(f"Ocorreu um erro durante o teletransporte: {e}")

                        self.is_teleporting_dict.pop(usuário_alvo.id, Nenhum)
                        posição_final = Posição(1.0, 0.0, 14.5, "FrenteDireita")
                        aguarde self.teleport(usuário_alvo, posição_final)
                    

        se message.lower().startswith("ina") e aguarde self.is_user_allowed(usuário):
            target_username = mensagem.split("@")[-1].strip().lower()

            room_users = (aguarde self.highrise.get_room_users()).content
            target_user = next((u para u, _ em room_users se u.username.lower() == target_username), Nenhum)

            se target_user:
                self.is_teleporting_dict.pop(usuário_alvo.id, Nenhum)
                

        se message.lower() == "inat" e aguarde self.is_user_allowed(usuário):
            se self.following_user não for Nenhum:
                aguarde self.highrise.chat("oooo")
            outro:
                aguarde self.follow(usuário)

        se message.lower() == "inat" e aguarde self.is_user_allowed(usuário):
            se self.following_user não for Nenhum:
                aguarde self.highrise.chat("oooo.")
                self.following_user = Nenhum
            outro:
                aguarde self.highrise.chat("Você está esperando por kimseyi takip etmiyorum.")
              
        se message.lower().startswith("inativ") e aguarde self.is_user_allowed(usuário):
            partes = mensagem.split()
            se len(partes) != 2:
                retornar
            se "@" não estiver em partes[1]:
                nome de usuário = parts[1]
            outro:
                nome de usuário = partes[1][1:]

            room_users = (aguarde self.highrise.get_room_users()).content
            para room_user, pos em room_users:
                se room_user.username.lower() == username.lower():
                    user_id = usuário_da_sala.id
                    quebrar

            se "user_id" não estiver em locals():
                retornar

            tentar:
                aguarde self.highrise.moderate_room(user_id, "kick")
            exceto Exceção como e:
                retornar


      
        mensagem = mensagem.strip().lower()
        user_id = usuário.id
      
        se mensagem.startswith(""):
            emote_name = mensagem.replace("", "").strip()
            se user_id em self.user_emote_loops e self.user_emote_loops[user_id] == emote_name:
                aguarde self.stop_emote_loop(user_id)
            outro:
                aguarde self.start_emote_loop(id_do_usuário, nome_do_emote)
                
        se mensagem == "parar" ou mensagem == "dur" ou mensagem == "0":
            se user_id em self.user_emote_loops:
                aguarde self.stop_emote_loop(user_id)
                
        se mensagem == "dans":
            se user_id não estiver em self.user_emote_loops:
                aguarde self.start_random_emote_loop(user_id)
                
        se mensagem == "parar" ou mensagem == "dur":
            se user_id em self.user_emote_loops:
                se self.user_emote_loops[user_id] == "em":
                    aguarde self.stop_random_emote_loop(user_id)
     

        mensagem = mensagem.strip().lower()

        se "@" na mensagem:
            partes = mensagem.split("@")
            se len(partes) < 2:
                retornar

            nome_emote = partes[0].strip()
            target_username = partes[1].strip()

            se emote_name em emote_mapping:
                resposta = aguarde self.highrise.get_room_users()
                usuários = [content[0] para conteúdo em response.content]
                nomes de usuário = [user.username.lower() para usuário em usuários]

                se target_username não estiver em nomes de usuários:
                    retornar

                user_id = next((u.id para u em usuários se u.username.lower() == target_username), Nenhum)
                se não for user_id:
                    retornar

                aguarde self.handle_emote_command(usuário.id, nome_emote)
                aguarde self.handle_emote_command(id_do_usuário, nome_do_emote)


        para emote_name, emote_info em emote_mapping.items():
            se mensagem.lower() == emote_name.lower():
                tentar:
                    emote_a_enviar = emote_info["valor"]
                    aguarde self.highrise.send_emote(emote_para_enviar, user.id)
                exceto Exceção como e:
                    print(f"Erro ao enviar emote: {e}")


        se message.lower().startswith("Todos") e aguarde self.is_user_allowed(usuário):
            emote_name = message.replace("Todos", "").strip()
            se emote_name em emote_mapping:
                emote_a_enviar = mapeamento_de_emote[nome_de_emote]["valor"]
                room_users = (aguarde self.highrise.get_room_users()).content
                tarefas = []
                para room_user, _ em room_users:
                    tarefas.append(self.highrise.send_emote(emote_para_enviar, room_user.id))
                tentar:
                    aguarde asyncio.gather(*tarefas)
                exceto Exceção como e:
                    error_message = f"Erro ao enviar emotes: {e}"
                    aguarde self.highrise.send_whisper(usuário.id, mensagem_de_erro)
            outro:
                aguarde self.highrise.send_whisper(user.id, "Nome de emote inválido: {}".format(emote_name))
    
              
        mensagem = mensagem.strip().lower()

        tentar:
            se message.lstrip().startswith("ina"):
                resposta = aguarde self.highrise.get_room_users()
                usuários = [content[0] para conteúdo em response.content]
                nomes de usuário = [user.username.lower() para usuário em usuários]
                partes = mensagem[1:].split()
                args = partes[1:]

                se len(args) >= 1 e args[0][0] == "@" e args[0][1:].lower() em nomes de usuários:
                    user_id = next((u.id para u em usuários se u.username.lower() == args[0][1:].lower()), Nenhum)

                    se mensagem.lower().startswith("ina"):
                        aguarde self.highrise.send_emote("emote-telekinesis", user.id)
                        aguarde self.highrise.send_emote("emote-gravity", user_id)
        exceto Exceção como e:
            print(f"Ocorreu um erro: {e}")
          
        se message.startswith("Hso") ou message.startswith("danslar"):
            tentar:
                emote_name = random.choice(lista(secili_emote.keys()))
                emote_a_enviar = secili_emote[nome_emote]["valor"]
                aguarde self.highrise.send_emote(emote_para_enviar, user.id)
            exceto:
                imprimir("ØØ¯Ø« Ø®Ø·Ø£ Ø£Ø«Ù†Ø§Ø¡ Ø¥Ø±Ø³Ø§Ù„ ØªØ¹Ø¨ÙŠØ± Ø§Ù„Ø±Ù‚ØµØ©.")


#NumaralÄ± emotlar numaralÄ± emotlar
  
    async def handle_emote_command(self, user_id: str, emote_name: str) -> Nenhum:
        se emote_name em emote_mapping:
            emote_info = mapeamento_de_emote[nome_de_emote]
            emote_a_enviar = emote_info["valor"]

            tentar:
                aguarde self.highrise.send_emote(emote_para_enviar, user_id)
            exceto Exceção como e:
                print(f"Erro ao enviar emote: {e}")


    async def start_emote_loop(self, user_id: str, emote_name: str) -> Nenhum:
        se emote_name em emote_mapping:
            self.user_emote_loops[id_do_usuário] = nome_do_emote
            emote_info = mapeamento_de_emote[nome_de_emote]
            emote_a_enviar = emote_info["valor"]
            emote_time = emote_info["tempo"]

            enquanto self.user_emote_loops.get(user_id) == emote_name:
                tentar:
                    aguarde self.highrise.send_emote(emote_para_enviar, user_id)
                exceto Exceção como e:
                    se "Usuário alvo não está na sala" em str(e):
                        print(f"{user_id} odada deÄŸil, emote gÃ¶nderme durduruluyor.")
                        quebrar
                aguarde asyncio.sleep(emote_time)

    async def stop_emote_loop(self, user_id: str) -> Nenhum:
        se user_id em self.user_emote_loops:
            self.user_emote_loops.pop(id_do_usuário)


  
#emotes pagos emotes pagos emotes pagos
  
    assíncrono def emote_loop(self):
        enquanto Verdadeiro:
            tentar:
                emote_name = random.choice(lista(emotes_pagos.keys()))
                emote_a_enviar = emotes_pagos[nome_do_emote]["valor"]
                emote_time = emotes_pagos[nome_emote]["tempo"]
                
                aguarde self.highrise.send_emote(emote_id=emote_to_send)
                aguarde asyncio.sleep(emote_time)
            exceto Exceção como e:
                print("Erro ao enviar emote:", e)


  
#Ulti Ulti Ulti Ulti Ulti Ulti Ulti

    async def start_random_emote_loop(self, user_id: str) -> Nenhum:
        self.user_emote_loops[id_do_usuário] = "rb"
        enquanto self.user_emote_loops.get(user_id) == "sp":
            tentar:
                emote_name = random.choice(lista(secili_emote.keys()))
                emote_info = secili_emote[nome_emote]
                emote_a_enviar = emote_info["valor"]
                emote_time = emote_info["tempo"]
                aguarde self.highrise.send_emote(emote_para_enviar, user_id)
                aguarde asyncio.sleep(emote_time)
            exceto Exceção como e:
                print(f"Erro ao enviar emote aleatório: {e}")

    async def stop_random_emote_loop(self, user_id: str) -> Nenhum:
        se user_id em self.user_emote_loops:
            do self.user_emote_loops[id_do_usuário]



  #Genel Genel Genel Genel Genel See More

    async def send_emote(self, emote_para_enviar: str, user_id: str) -> Nenhum:
        aguarde self.highrise.send_emote(emote_para_enviar, user_id)
      


    async def on_whisper(self, usuário: Usuário, mensagem: str) -> Nenhum:
        """Em um sussurro de sala recebido."""
        se aguardar self.is_user_allowed(usuário) e message.startswith(''):
            tentar:
                xxx = mensagem[0:]
                aguarde self.highrise.chat(xxx)
            exceto:
                imprimir("erro 3")
  
    async def is_user_allowed(self, usuário: Usuário) -> bool:
        user_privileges = aguarde self.highrise.get_room_privilege(user.id)
        retornar user_privileges.moderator ou user.username em ["c1q"]

#gellllbbb

    async def sala_moderada(
        auto,
        ID do usuário: str,
        ação: Literal["chutar", "banir", "desbanir", "silenciar"],
        action_length: int | Nenhum = Nenhum,
    ) -> Nenhum:
        """Moderar um usuário na sala."""
  
    async def userinfo(self, user: Usuário, target_username: str) -> Nenhum:
        user_info = await self.webapi.get_users(nome_de_usuário=nome_de_usuário_de_alvo, limite=1)

        se não for user_info.users:
            await self.highrise.chat("Ù„Ù… ÙŠØªÙ… Ø§Ù„Ø¹Ø«ÙˆØ± Ø¹Ù„Ù‰ Ø§Ù„Ù…Ø³ØªØ®Ø¯Ù…ØŒ ÙŠØ±Ø¬Ù‰ ØªØØ¯Ù ŠØ¯Ù …Ø³ØªØ®Ø¯Ù… ØµØ§Ù„Ø")
            retornar

        id_usuário = info_usuário.usuários[0].id_usuário

        user_info = aguarde self.webapi.get_user(id_usuário)

        número_de_seguidores = user_info.user.num_followers
        número_de_amigos = user_info.user.num_friends
        código_país = info_usuário.usuário.código_país
        roupa = user_info.user.outfit
        bio = user_info.usuário.bio
        active_room = info_do_usuário.usuário.active_room
        tripulação = user_info.user.crew
        número_de_seguidores = user_info.user.num_following
        join_at = user_info.user.joined_at.strftime("%d/%m/%Y %H:%M:%S")

        data_de_ingresso = user_info.user.joined_at.date()
        hoje = datetime.now().date()
        dias_jogados = (hoje - data_de_entrada).dias

        last_login = user_info.user.last_online_in.strftime("%d/%m/%Y %H:%M:%S") if user_info.user.last_online_in else "Seu login será bloqueado novamente"

        await self.highrise.chat(f"""Nome: {target_username}\nSeguidores: {number_of_followers}\nAmigos: {number_of_friends}\nEntrada: {joined_at}\nDias jogados: {days_played}""")

    async def follow(self, usuário: Usuário, mensagem: str = ""):
        self.following_user = usuário  
        enquanto self.following_user == usuário:
            room_users = (aguarde self.highrise.get_room_users()).content
            para room_user, posição em room_users:
                se room_user.id == user.id:
                    user_position = posição
                    quebrar
            se user_position não for None e isinstance(user_position, Position):
                posição_próxima = Posição(posição_usuário.x + 1.0, posição_usuário.y, posição_usuário.z)
                aguarde self.highrise.walk_to(posição_próxima)
            
            aguarde asyncio.sleep(0.5)
  
    async def adjust_position(self, usuário: Usuário, mensagem: str, eixo: str) -> Nenhum:
        tentar:
            ajuste = int(mensagem[2:])
            se mensagem.startswith("-"):
                ajuste *= -1

            room_users = aguardar self.highrise.get_room_users()
            user_position = Nenhum

            para user_obj, user_position em room_users.content:
                se user_obj.id == user.id:
                    quebrar

            se user_position:
                nova_posição = Nenhuma

                se eixo == 'x':
                    nova_posição = Posição(posição_usuário.x + ajuste, posição_usuário.y, posição_usuário.z, posição_usuário.voltado)
                eixo elif == 'y':
                    nova_posição = Posição(posição_usuário.x, posição_usuário.y + ajuste, posição_usuário.z, posição_usuário.voltado)
                eixo elif == 'z':
                    nova_posição = Posição(posição_usuário.x, posição_usuário.y, posição_usuário.z + ajuste, posição_usuário.voltado)
                outro:
                    print(f"Eixo não suportado: {eixo}")
                    retornar

                aguarde self.teleport(usuário, nova_posição)

        exceto ValueError:
            print("Valor de ajuste inválido. Use +x/-x, +y/-y ou +z/-z seguido de um inteiro.")
        exceto Exceção como e:
            print(f"Ocorreu um erro durante o ajuste de posição: {e}")
  
    async def switch_users(self, user: Usuário, target_username: str) -> Nenhum:
        tentar:
            room_users = aguardar self.highrise.get_room_users()

            maker_position = Nenhum
            para maker_user, maker_position em room_users.content:
                se maker_user.id == user.id:
                    quebrar

            target_position = Nenhum
            para target_user, posição em room_users.content:
                se target_user.username.lower() == target_username.lower():
                    target_position = posição
                    quebrar

            se maker_position e target_position:
                aguarde self.teleport(usuário, Posição(posição_alvo.x + 0,0001, posição_alvo.y, posição_alvo.z, posição_alvo.facing))

                aguarde self.teleport(usuário_alvo, Posição(posição_do_fabricante.x + 0,0001, posição_do_fabricante.y, posição_do_fabricante.z, posição_do_fabricante.facing))

        exceto Exceção como e:
            print(f"Ocorreu um erro durante a troca de usuário: {e}")

    async def teleport(self, usuário: Usuário, posição: Posição):
        tentar:
            aguarde self.highrise.teleport(usuário.id, posição)
        exceto Exceção como e:
            print(f"Erro de teletransporte detectado: {e}")

    async def teleport_to_user(self, user: Usuário, target_username: str) -> Nenhum:
        tentar:
            room_users = aguardar self.highrise.get_room_users()
            para alvo, posição em room_users.content:
                se target.username.lower() == target_username.lower():
                    z = posição.z
                    novo_z = z - 1
                    aguarde self.teleport(usuário, Posição(posição.x, posição.y, new_z, posição.facing))
                    quebrar
        exceto Exceção como e:
            print(f"Ocorreu um erro ao teletransportar para {target_username}: {e}")

    async def teleport_user_next_to(self, target_username: str, requester_user: Usuário) -> Nenhum:
        tentar:

            room_users = aguardar self.highrise.get_room_users()
            requester_position = Nenhum
            para usuário, posição em room_users.content:
                se user.id == requester_user.id:
                    requester_position = posição
                    quebrar


          
            para usuário, posição em room_users.content:
                se usuário.nomedeusuário.lower() == nome_usuário_alvo.lower():
                    z = posição_do_solicitante.z
                    novo_z = z + 1  
                    aguarde self.teleport(usuário, Posição(posição_do_solicitante.x, posição_do_solicitante.y, novo_z, posição_do_solicitante.facing))
                    quebrar
        exceto Exceção como e:
            print(f"Ocorreu um erro ao teletransportar {target_username} para perto de {requester_user.username}: {e}")

    async def on_tip(self, remetente: Usuário, destinatário: Usuário, dica: CurrencyItem | Item) -> Nenhum:
        message = f"{sender.username} Mandou para {receiver.username} total {tip.amount} ouro."
        aguarde self.highrise.chat(mensagem)
  
    async def reset_target_position(self, target_user_obj: Usuário, initial_position: Posição) -> Nenhum:
        tentar:
            enquanto Verdadeiro:
                room_users = aguardar self.highrise.get_room_users()
                current_position = next((posição para usuário, posição em room_users.content se user.id == target_user_obj.id), Nenhum)

                se current_position e current_position != initial_position:
                    aguarde self.teleport(obj_usuário_alvo, posição_inicial)

                aguarde asyncio.sleep(1)

        exceto asyncio.CancelledError:
            passar
        exceto Exceção como e:
            print(f"Ocorreu um erro durante o monitoramento de posição: {e}")  
  
  
    async def run(self, room_id, token) -> Nenhum:
        aguarde __main__.main(self, room_id, token)
classe WebServer():

  def __init__(próprio):
    self.app = Flask(__nome__)

    @self.app.route('/')
    def índice() -> str:
      retornar "Vivo"

  def run(self) -> Nenhum:
    self.app.run(host='0.0.0.0', porta=8080)

  def keep_alive(self):
    t = Thread(alvo=self.run)
    t.iniciar()
    
classe RunBot():
  room_id = "65aac8e0f2cf8085d613f717"
  bot_token = "dd1288edd48d05bb65e95bd80723408e4a6ad7dadf41a7f41db5b8fdf38e7cab"
  bot_file = "principal"
  bot_class = "Bot"

  def __init__(self) -> Nenhum:
    auto.definições = [
        Definição de Bot(
            getattr(import_module(self.bot_file), self.bot_class)(),
            self.id_da_sala, self.token_do_bot)
    ]

  def run_loop(self) -> Nenhum:
    enquanto Verdadeiro:
      tentar:
        arun(principal(self.definições))
      exceto Exceção como e:
        importação traceback
        print("Detectou uma exceção:")
        traceback.print_exc()
        tempo.sono(1)
        continuar


se __nome__ == "__principal__":
  Servidor Web().keep_alive()

  ExecutarBot().executar_loop()de importação de arranha-céus *
de highrise.models importar *
de asyncio importar executar como arun
do frasco importar frasco
de threading importar Thread
de highrise.__main__ importar *
de emotes importar*
importar aleatório
importar asyncio
tempo de importação

classe Bot(BaseBot):
    def __init__(próprio):
        super().__init__()
        self.emote_looping = Falso
        self.user_emote_loops = {}
        self.loop_task = Nenhum
        self.is_teleporting_dict = {}
        self.following_user = Nenhum
        self.following_user_id = Nenhum
        self.kus = {}
        self.posições_do_usuário = {}
        self.posição_tarefas = {}
        
    haricler = ["c1q","_5q"]

    async def on_emote(self, user: Usuário, emote_id: str, receiver: Usuário | Nenhum) -> Nenhum:
      print(f"{user.username} emocionado: {emote_id}")
  
    async def on_start(self, session_metadata: SessionMetadata) -> Nenhum:
        print("oi, estou vivo?")
        aguarde self.highrise.tg.create_task(self.highrise.teleport(
            session_metadata.user_id, Posição( 13,00, 1,00, 5,00, "FrontRight")))
             

    async def on_user_join(self, usuário: Usuário, posição: Posição | AnchorPosition) -> Nenhum:
        await self.highrise.chat(f" Bem vindoðŸ– ï¸ sinta-se a vontade dono @DjLobin @{user.username} Emotes 0 - 96 ")
        tentar:
            emote_name = random.choice(lista(secili_emote.keys()))
            emote_info = secili_emote[nome_emote]
            emote_a_enviar = emote_info["valor"]
            aguarde self.send_emote(emote_para_enviar, user.id)
        exceto Exceção como e:
            print(f"Erro ao enviar emote para o usuário {user.id}: {e}")
  
    async def on_user_leave(self, usuário: Usuário):
    
        user_id = usuário.id
        farewell_message = f" volte logo ðŸ˜®â€ ðŸ'¨ðŸ'•! @{user.username}"
        se user_id em self.user_emote_loops:
            aguarde self.stop_emote_loop(user_id)
        aguarde self.highrise.chat(mensagem_de_despedida)
  

    async def on_chat(self, user: Usuário, mensagem: str) -> Nenhum:
        """Em um bate-papo recebido em toda a sala."""    

        se mensagem.lower().startswith("Ä "):
          aguarde self.highrise.send_emote("emote-kiss")

        isimler1 = [
            "\n1 - @",
            "\n2 - @",
            "\n3 - @",
            "\n4 - @",
            "\n5 - @",
        ]
        isimler2 = [
            "\n6 - @",
            "\n7 - @",
            "\n8 - @",
            "\n9 - @",
            "\n10 - @",
        ]
        isimler3 = [
            "\n11 - @",
            "\n12 - @",
            "\n13 - @",
            "\n14 - @",
            "\n15 - @",
        ]
        isimler4 = [
            "\n16 - @",
            "\n17 - @",
            "\n18 - @",
            "\n19 - @",
            "\n20 - @",
        ]
        isimler5 = [
            "\n21 - @",
            "\n22 - @",
            "\n23 - @",
            "\n24 - @",
            "\n25 - @",
            "\n26 - @"

            # DiÄŸer isimler buraya eklenecek
        ]

        
        se mensagem.lower().startswith("Ä "):
          aguarde self.highrise.chat("\n".join(isimler1))
          aguarde self.highrise.chat("\n".join(isimler2))
          aguarde self.highrise.chat("\n".join(isimler3))
          aguarde self.highrise.chat("\n".join(isimler4))
          aguarde self.highrise.chat("\n".join(isimler5))
          aguarde self.highrise.chat(f"\n\nÃ–nerileriniz için")

          


        mensagem = mensagem.lower()

        localizações_de_teletransporte = {
            "vip1": Posição(3,00, 0,00, 0,00),
            "vip2": Posição(13.5, 11.0, 7.5),
            "vip3": Posição(11., 1., 11.),
            "deneme1": Posição(random.randint(0, 40), random.randint(0, 40), random.randint(0, 40)),
            "deneme1": Posição(random.randint(0, 40), random.randint(0, 40), random.randint(0, 40))
        }

        para location_name, posição em teleport_locations.items():
            se mensagem ==(nome_do_local):
                tentar:
                    aguarde self.teleport(usuário, posição)
                exceto:
                    print("Ocorreu um erro durante o teletransporte")
                  
        se message.lower().startswith("ina") e aguarde self.is_user_allowed(usuário):
            target_username = mensagem.split("@")[-1].strip()
            room_users = aguardar self.highrise.get_room_users()
            user_info = next((info para informações em room_users.content se info[0].username.lower() == target_username.lower()), Nenhum)

            se user_info:
                target_user_obj, posição_inicial = info_do_usuário
                tarefa = asyncio.create_task(self.reset_target_position(obj_usuário_alvo, posição_inicial))

                se target_user_obj.id não estiver em self.position_tasks:
                    self.position_tasks[objeto_usuário_alvo.id] = []
                self.position_tasks[obj.id_usuário_alvo].append(tarefa)

        elif message.lower().startswith("ina") e aguarde self.is_user_allowed(usuário):
            target_username = mensagem.split("@")[-1].strip()
            room_users = aguardar self.highrise.get_room_users()
            target_user_obj = next((user_obj para user_obj, _ em room_users.content se user_obj.username.lower() == target_username.lower()), Nenhum)

            se target_user_obj:
                tarefas = self.position_tasks.pop(objeto_usuário_alvo.id, [])
                para tarefa em tarefas:
                    tarefa.cancelar()
                print(f"Interrompendo o loop de monitoramento de posição para {target_username}")
            outro:
                print(f"Usuário {target_username} não encontrado na sala.")

        se mensagem.lower().startswith("info"):
            target_username = mensagem.split("@")[-1].strip()
            aguarde self.userinfo(usuário, nome_de_usuário_alvo)


        se message.startswith("+x") ou message.startswith("-x"):
            aguarde self.adjust_position(usuário, mensagem, 'x')
        mensagem elif.startswith("+y") ou mensagem.startswith("-y"):
            aguarde self.adjust_position(usuário, mensagem, 'y')
        mensagem elif.startswith("+z") ou mensagem.startswith("-z"):
            aguarde self.adjust_position(usuário, mensagem, 'z')
              
      
        allowed_commands = ["switch", "degis", "deÄŸiÅŸ","deÄŸis","degiÅŸ"]
        se houver algum (message.lower().startswith(command) para comando em allowed_commands) e aguarde self.is_user_allowed(user):
            target_username = mensagem.split("@")[-1].strip()

        
            se target_username não estiver em self.haricler:
                aguarde self.switch_users(usuário, nome_de_usuário_alvo)
            outro:
                print(f"{target_username} está na lista de exclusão e não será afetado pela troca.")

        se message.lower().startswith("Tp") ou message.lower().startswith("tp"):
          target_username = mensagem.split("@")[-1].strip()
          aguarde self.teleport_to_user(usuário, nome_de_usuário_alvo)
        se aguardar self.is_user_allowed(usuário) e message.lower().startswith("T"):
            target_username = mensagem.split("@")[-1].strip()
            se target_username não estiver em self.haricler:
                aguarde self.teleport_user_next_to(nome_de_usuário_de_destino, usuário)
        se message.lower().startswith("--") e aguarde self.is_user_allowed(usuário):
            partes = mensagem.split()
            se len(partes) == 2 e parts[1].startswith("@"):
                target_username = partes[1][1:]
                target_user = Nenhum

                room_users = (aguarde self.highrise.get_room_users()).content
                para room_user, _ em room_users:
                    se room_user.username.lower() == target_username e room_user.username.lower() não estiverem em self.haricler:
                        target_user = usuário_da_sala
                        quebrar

                se target_user:
                    tentar:
                        kl = Posição(random.randint(0, 40), random.randint(0, 40), random.randint(0, 40))
                        aguarde self.teleport(target_user, kl)
                    exceto Exceção como e:
                        print(f"Ocorreu um erro durante o teletransporte: {e}")
                outro:
                    print(f"O nome do usuário alvo é '{target_username}' e o nome do usuário alvo é ')."

        se message.lower() == "rtp completo" ou message.lower() == "kaÃ§ completo":
            se user.id não estiver em self.kus:
                self.kus[user.id] = Falso

            se não self.kus[user.id]:
                self.kus[user.id] = Verdadeiro

                tentar:
                    enquanto self.kus.get(user.id, False):
                        kl = Posição(random.randint(0, 29), random.randint(0, 29), random.randint(0, 29))
                        aguarde self.teleport(usuário, kl)

                        aguarde asyncio.sleep(0.7)
                exceto Exceção como e:
                    print(f"Teleport sÄ±rasÄ±nda bir hata oluÅŸtu: {e}")

        se message.lower() == "dur" ou message.lower() == "stop":
            se user.id em self.kus:
                self.kus[user.id] = Falso

        se message.lower().startswith("ina") e aguarde self.is_user_allowed(usuário):
            target_username = mensagem.split("@")[-1].strip().lower()

            se target_username não estiver em self.haricler:
                room_users = (aguarde self.highrise.get_room_users()).content
                target_user = next((u para u, _ em room_users se u.username.lower() == target_username), Nenhum)

                se target_user:
                    se target_user.id não estiver em self.is_teleporting_dict:
                        self.is_teleporting_dict[target_user.id] = Verdadeiro

                        tentar:
                            enquanto self.is_teleporting_dict.get(target_user.id, False):
                                kl = Posição(random.randint(0, 39), random.randint(0, 29), random.randint(0, 39))
                                aguarde self.teleport(target_user, kl)
                                aguarde asyncio.sleep(1)
                        exceto Exceção como e:
                            print(f"Ocorreu um erro durante o teletransporte: {e}")

                        self.is_teleporting_dict.pop(usuário_alvo.id, Nenhum)
                        posição_final = Posição(1.0, 0.0, 14.5, "FrenteDireita")
                        aguarde self.teleport(usuário_alvo, posição_final)
                    

        se message.lower().startswith("ina") e aguarde self.is_user_allowed(usuário):
            target_username = mensagem.split("@")[-1].strip().lower()

            room_users = (aguarde self.highrise.get_room_users()).content
            target_user = next((u para u, _ em room_users se u.username.lower() == target_username), Nenhum)

            se target_user:
                self.is_teleporting_dict.pop(usuário_alvo.id, Nenhum)
                

        se message.lower() == "inat" e aguarde self.is_user_allowed(usuário):
            se self.following_user não for Nenhum:
                aguarde self.highrise.chat("oooo")
            outro:
                aguarde self.follow(usuário)

        se message.lower() == "inat" e aguarde self.is_user_allowed(usuário):
            se self.following_user não for Nenhum:
                aguarde self.highrise.chat("oooo.")
                self.following_user = Nenhum
            outro:
                aguarde self.highrise.chat("Você está esperando por kimseyi takip etmiyorum.")
              
        se message.lower().startswith("inativ") e aguarde self.is_user_allowed(usuário):
            partes = mensagem.split()
            se len(partes) != 2:
                retornar
            se "@" não estiver em partes[1]:
                nome de usuário = parts[1]
            outro:
                nome de usuário = partes[1][1:]

            room_users = (aguarde self.highrise.get_room_users()).content
            para room_user, pos em room_users:
                se room_user.username.lower() == username.lower():
                    user_id = usuário_da_sala.id
                    quebrar

            se "user_id" não estiver em locals():
                retornar

            tentar:
                aguarde self.highrise.moderate_room(user_id, "kick")
            exceto Exceção como e:
                retornar


      
        mensagem = mensagem.strip().lower()
        user_id = usuário.id
      
        se mensagem.startswith(""):
            emote_name = mensagem.replace("", "").strip()
            se user_id em self.user_emote_loops e self.user_emote_loops[user_id] == emote_name:
                aguarde self.stop_emote_loop(user_id)
            outro:
                aguarde self.start_emote_loop(id_do_usuário, nome_do_emote)
                
        se mensagem == "parar" ou mensagem == "dur" ou mensagem == "0":
            se user_id em self.user_emote_loops:
                aguarde self.stop_emote_loop(user_id)
                
        se mensagem == "dans":
            se user_id não estiver em self.user_emote_loops:
                aguarde self.start_random_emote_loop(user_id)
                
        se mensagem == "parar" ou mensagem == "dur":
            se user_id em self.user_emote_loops:
                se self.user_emote_loops[user_id] == "em":
                    aguarde self.stop_random_emote_loop(user_id)
     

        mensagem = mensagem.strip().lower()

        se "@" na mensagem:
            partes = mensagem.split("@")
            se len(partes) < 2:
                retornar

            nome_emote = partes[0].strip()
            target_username = partes[1].strip()

            se emote_name em emote_mapping:
                resposta = aguarde self.highrise.get_room_users()
                usuários = [content[0] para conteúdo em response.content]
                nomes de usuário = [user.username.lower() para usuário em usuários]

                se target_username não estiver em nomes de usuários:
                    retornar

                user_id = next((u.id para u em usuários se u.username.lower() == target_username), Nenhum)
                se não for user_id:
                    retornar

                aguarde self.handle_emote_command(usuário.id, nome_emote)
                aguarde self.handle_emote_command(id_do_usuário, nome_do_emote)


        para emote_name, emote_info em emote_mapping.items():
            se mensagem.lower() == emote_name.lower():
                tentar:
                    emote_a_enviar = emote_info["valor"]
                    aguarde self.highrise.send_emote(emote_para_enviar, user.id)
                exceto Exceção como e:
                    print(f"Erro ao enviar emote: {e}")


        se message.lower().startswith("Todos") e aguarde self.is_user_allowed(usuário):
            emote_name = message.replace("Todos", "").strip()
            se emote_name em emote_mapping:
                emote_a_enviar = mapeamento_de_emote[nome_de_emote]["valor"]
                room_users = (aguarde self.highrise.get_room_users()).content
                tarefas = []
                para room_user, _ em room_users:
                    tarefas.append(self.highrise.send_emote(emote_para_enviar, room_user.id))
                tentar:
                    aguarde asyncio.gather(*tarefas)
                exceto Exceção como e:
                    error_message = f"Erro ao enviar emotes: {e}"
                    aguarde self.highrise.send_whisper(usuário.id, mensagem_de_erro)
            outro:
                aguarde self.highrise.send_whisper(user.id, "Nome de emote inválido: {}".format(emote_name))
    
              
        mensagem = mensagem.strip().lower()

        tentar:
            se message.lstrip().startswith("ina"):
                resposta = aguarde self.highrise.get_room_users()
                usuários = [content[0] para conteúdo em response.content]
                nomes de usuário = [user.username.lower() para usuário em usuários]
                partes = mensagem[1:].split()
                args = partes[1:]

                se len(args) >= 1 e args[0][0] == "@" e args[0][1:].lower() em nomes de usuários:
                    user_id = next((u.id para u em usuários se u.username.lower() == args[0][1:].lower()), Nenhum)

                    se mensagem.lower().startswith("ina"):
                        aguarde self.highrise.send_emote("emote-telekinesis", user.id)
                        aguarde self.highrise.send_emote("emote-gravity", user_id)
        exceto Exceção como e:
            print(f"Ocorreu um erro: {e}")
          
        se message.startswith("Hso") ou message.startswith("danslar"):
            tentar:
                emote_name = random.choice(lista(secili_emote.keys()))
                emote_a_enviar = secili_emote[nome_emote]["valor"]
                aguarde self.highrise.send_emote(emote_para_enviar, user.id)
            exceto:
                imprimir("ØØ¯Ø« Ø®Ø·Ø£ Ø£Ø«Ù†Ø§Ø¡ Ø¥Ø±Ø³Ø§Ù„ ØªØ¹Ø¨ÙŠØ± Ø§Ù„Ø±Ù‚ØµØ©.")


#NumaralÄ± emotlar numaralÄ± emotlar
  
    async def handle_emote_command(self, user_id: str, emote_name: str) -> Nenhum:
        se emote_name em emote_mapping:
            emote_info = mapeamento_de_emote[nome_de_emote]
            emote_a_enviar = emote_info["valor"]

            tentar:
                aguarde self.highrise.send_emote(emote_para_enviar, user_id)
            exceto Exceção como e:
                print(f"Erro ao enviar emote: {e}")


    async def start_emote_loop(self, user_id: str, emote_name: str) -> Nenhum:
        se emote_name em emote_mapping:
            self.user_emote_loops[id_do_usuário] = nome_do_emote
            emote_info = mapeamento_de_emote[nome_de_emote]
            emote_a_enviar = emote_info["valor"]
            emote_time = emote_info["tempo"]

            enquanto self.user_emote_loops.get(user_id) == emote_name:
                tentar:
                    aguarde self.highrise.send_emote(emote_para_enviar, user_id)
                exceto Exceção como e:
                    se "Usuário alvo não está na sala" em str(e):
                        print(f"{user_id} odada deÄŸil, emote gÃ¶nderme durduruluyor.")
                        quebrar
                aguarde asyncio.sleep(emote_time)

    async def stop_emote_loop(self, user_id: str) -> Nenhum:
        se user_id em self.user_emote_loops:
            self.user_emote_loops.pop(id_do_usuário)


  
#emotes pagos emotes pagos emotes pagos
  
    assíncrono def emote_loop(self):
        enquanto Verdadeiro:
            tentar:
                emote_name = random.choice(lista(emotes_pagos.keys()))
                emote_a_enviar = emotes_pagos[nome_do_emote]["valor"]
                emote_time = emotes_pagos[nome_emote]["tempo"]
                
                aguarde self.highrise.send_emote(emote_id=emote_to_send)
                aguarde asyncio.sleep(emote_time)
            exceto Exceção como e:
                print("Erro ao enviar emote:", e)


  
#Ulti Ulti Ulti Ulti Ulti Ulti Ulti

    async def start_random_emote_loop(self, user_id: str) -> Nenhum:
        self.user_emote_loops[id_do_usuário] = "rb"
        enquanto self.user_emote_loops.get(user_id) == "sp":
            tentar:
                emote_name = random.choice(lista(secili_emote.keys()))
                emote_info = secili_emote[nome_emote]
                emote_a_enviar = emote_info["valor"]
                emote_time = emote_info["tempo"]
                aguarde self.highrise.send_emote(emote_para_enviar, user_id)
                aguarde asyncio.sleep(emote_time)
            exceto Exceção como e:
                print(f"Erro ao enviar emote aleatório: {e}")

    async def stop_random_emote_loop(self, user_id: str) -> Nenhum:
        se user_id em self.user_emote_loops:
            do self.user_emote_loops[id_do_usuário]



  #Genel Genel Genel Genel Genel See More

    async def send_emote(self, emote_para_enviar: str, user_id: str) -> Nenhum:
        aguarde self.highrise.send_emote(emote_para_enviar, user_id)
      


    async def on_whisper(self, usuário: Usuário, mensagem: str) -> Nenhum:
        """Em um sussurro de sala recebido."""
        se aguardar self.is_user_allowed(usuário) e message.startswith(''):
            tentar:
                xxx = mensagem[0:]
                aguarde self.highrise.chat(xxx)
            exceto:
                imprimir("erro 3")
  
    async def is_user_allowed(self, usuário: Usuário) -> bool:
        user_privileges = aguarde self.highrise.get_room_privilege(user.id)
        retornar user_privileges.moderator ou user.username em ["c1q"]

#gellllbbb

    async def sala_moderada(
        auto,
        ID do usuário: str,
        ação: Literal["chutar", "banir", "desbanir", "silenciar"],
        action_length: int | Nenhum = Nenhum,
    ) -> Nenhum:
        """Moderar um usuário na sala."""
  
    async def userinfo(self, user: Usuário, target_username: str) -> Nenhum:
        user_info = await self.webapi.get_users(nome_de_usuário=nome_de_usuário_de_alvo, limite=1)

        se não for user_info.users:
            await self.highrise.chat("Ù„Ù… ÙŠØªÙ… Ø§Ù„Ø¹Ø«ÙˆØ± Ø¹Ù„Ù‰ Ø§Ù„Ù…Ø³ØªØ®Ø¯Ù…ØŒ ÙŠØ±Ø¬Ù‰ ØªØØ¯Ù ŠØ¯Ù …Ø³ØªØ®Ø¯Ù… ØµØ§Ù„Ø")
            retornar

        id_usuário = info_usuário.usuários[0].id_usuário

        user_info = aguarde self.webapi.get_user(id_usuário)

        número_de_seguidores = user_info.user.num_followers
        número_de_amigos = user_info.user.num_friends
        código_país = info_usuário.usuário.código_país
        roupa = user_info.user.outfit
        bio = user_info.usuário.bio
        active_room = info_do_usuário.usuário.active_room
        tripulação = user_info.user.crew
        número_de_seguidores = user_info.user.num_following
        join_at = user_info.user.joined_at.strftime("%d/%m/%Y %H:%M:%S")

        data_de_ingresso = user_info.user.joined_at.date()
        hoje = datetime.now().date()
        dias_jogados = (hoje - data_de_entrada).dias

        last_login = user_info.user.last_online_in.strftime("%d/%m/%Y %H:%M:%S") if user_info.user.last_online_in else "Seu login será bloqueado novamente"

        await self.highrise.chat(f"""Nome: {target_username}\nSeguidores: {number_of_followers}\nAmigos: {number_of_friends}\nEntrada: {joined_at}\nDias jogados: {days_played}""")

    async def follow(self, usuário: Usuário, mensagem: str = ""):
        self.following_user = usuário  
        enquanto self.following_user == usuário:
            room_users = (aguarde self.highrise.get_room_users()).content
            para room_user, posição em room_users:
                se room_user.id == user.id:
                    user_position = posição
                    quebrar
            se user_position não for None e isinstance(user_position, Position):
                posição_próxima = Posição(posição_usuário.x + 1.0, posição_usuário.y, posição_usuário.z)
                aguarde self.highrise.walk_to(posição_próxima)
            
            aguarde asyncio.sleep(0.5)
  
    async def adjust_position(self, usuário: Usuário, mensagem: str, eixo: str) -> Nenhum:
        tentar:
            ajuste = int(mensagem[2:])
            se mensagem.startswith("-"):
                ajuste *= -1

            room_users = aguardar self.highrise.get_room_users()
            user_position = Nenhum

            para user_obj, user_position em room_users.content:
                se user_obj.id == user.id:
                    quebrar

            se user_position:
                nova_posição = Nenhuma

                se eixo == 'x':
                    nova_posição = Posição(posição_usuário.x + ajuste, posição_usuário.y, posição_usuário.z, posição_usuário.voltado)
                eixo elif == 'y':
                    nova_posição = Posição(posição_usuário.x, posição_usuário.y + ajuste, posição_usuário.z, posição_usuário.voltado)
                eixo elif == 'z':
                    nova_posição = Posição(posição_usuário.x, posição_usuário.y, posição_usuário.z + ajuste, posição_usuário.voltado)
                outro:
                    print(f"Eixo não suportado: {eixo}")
                    retornar

                aguarde self.teleport(usuário, nova_posição)

        exceto ValueError:
            print("Valor de ajuste inválido. Use +x/-x, +y/-y ou +z/-z seguido de um inteiro.")
        exceto Exceção como e:
            print(f"Ocorreu um erro durante o ajuste de posição: {e}")
  
    async def switch_users(self, user: Usuário, target_username: str) -> Nenhum:
        tentar:
            room_users = aguardar self.highrise.get_room_users()

            maker_position = Nenhum
            para maker_user, maker_position em room_users.content:
                se maker_user.id == user.id:
                    quebrar

            target_position = Nenhum
            para target_user, posição em room_users.content:
                se target_user.username.lower() == target_username.lower():
                    target_position = posição
                    quebrar

            se maker_position e target_position:
                aguarde self.teleport(usuário, Posição(posição_alvo.x + 0,0001, posição_alvo.y, posição_alvo.z, posição_alvo.facing))

                aguarde self.teleport(usuário_alvo, Posição(posição_do_fabricante.x + 0,0001, posição_do_fabricante.y, posição_do_fabricante.z, posição_do_fabricante.facing))

        exceto Exceção como e:
            print(f"Ocorreu um erro durante a troca de usuário: {e}")

    async def teleport(self, usuário: Usuário, posição: Posição):
        tentar:
            aguarde self.highrise.teleport(usuário.id, posição)
        exceto Exceção como e:
            print(f"Erro de teletransporte detectado: {e}")

    async def teleport_to_user(self, user: Usuário, target_username: str) -> Nenhum:
        tentar:
            room_users = aguardar self.highrise.get_room_users()
            para alvo, posição em room_users.content:
                se target.username.lower() == target_username.lower():
                    z = posição.z
                    novo_z = z - 1
                    aguarde self.teleport(usuário, Posição(posição.x, posição.y, new_z, posição.facing))
                    quebrar
        exceto Exceção como e:
            print(f"Ocorreu um erro ao teletransportar para {target_username}: {e}")

    async def teleport_user_next_to(self, target_username: str, requester_user: Usuário) -> Nenhum:
        tentar:

            room_users = aguardar self.highrise.get_room_users()
            requester_position = Nenhum
            para usuário, posição em room_users.content:
                se user.id == requester_user.id:
                    requester_position = posição
                    quebrar


          
            para usuário, posição em room_users.content:
                se usuário.nomedeusuário.lower() == nome_usuário_alvo.lower():
                    z = posição_do_solicitante.z
                    novo_z = z + 1  
                    aguarde self.teleport(usuário, Posição(posição_do_solicitante.x, posição_do_solicitante.y, novo_z, posição_do_solicitante.facing))
                    quebrar
        exceto Exceção como e:
            print(f"Ocorreu um erro ao teletransportar {target_username} para perto de {requester_user.username}: {e}")

    async def on_tip(self, remetente: Usuário, destinatário: Usuário, dica: CurrencyItem | Item) -> Nenhum:
        message = f"{sender.username} Mandou para {receiver.username} total {tip.amount} ouro."
        aguarde self.highrise.chat(mensagem)
  
    async def reset_target_position(self, target_user_obj: Usuário, initial_position: Posição) -> Nenhum:
        tentar:
            enquanto Verdadeiro:
                room_users = aguardar self.highrise.get_room_users()
                current_position = next((posição para usuário, posição em room_users.content se user.id == target_user_obj.id), Nenhum)

                se current_position e current_position != initial_position:
                    aguarde self.teleport(obj_usuário_alvo, posição_inicial)

                aguarde asyncio.sleep(1)

        exceto asyncio.CancelledError:
            passar
        exceto Exceção como e:
            print(f"Ocorreu um erro durante o monitoramento de posição: {e}")  
  
  
    async def run(self, room_id, token) -> Nenhum:
        aguarde __main__.main(self, room_id, token)
classe WebServer():

  def __init__(próprio):
    self.app = Flask(__nome__)

    @self.app.route('/')
    def índice() -> str:
      retornar "Vivo"

  def run(self) -> Nenhum:
    self.app.run(host='0.0.0.0', porta=8080)

  def keep_alive(self):
    t = Thread(alvo=self.run)
    t.iniciar()
    
classe RunBot():
  room_id = "65aac8e0f2cf8085d613f717"
  bot_token = "dd1288edd48d05bb65e95bd80723408e4a6ad7dadf41a7f41db5b8fdf38e7cab"
  bot_file = "principal"
  bot_class = "Bot"

  def __init__(self) -> Nenhum:
    auto.definições = [
        Definição de Bot(
            getattr(import_module(self.bot_file), self.bot_class)(),
            self.id_da_sala, self.token_do_bot)
    ]

  def run_loop(self) -> Nenhum:
    enquanto Verdadeiro:
      tentar:
        arun(principal(self.definições))
      exceto Exceção como e:
        importação traceback
        print("Detectou uma exceção:")
        traceback.print_exc()
        tempo.sono(1)
        continuar


se __nome__ == "__principal__":https://replit.com/@JonatasCarvalh2/Teste-1-hero?s=appmain.py
  Servidor Web().keep_alive()

  ExecutarBot().executar_loop()echo "# Highrise-" >> README.md 
git init 
git add README.md 
git commit -m "primeiro commit" 
git branch -M main 
git remote add origin https://github.com/HeroJohn08/Highrise-.git
 git push -u origin main
