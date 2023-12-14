'''python
import telebot
import random


bot = telebot.TeleBot('6650787715:AAF7RbbKyXl9JT9ZvTARvHbTrV7I35Ms1YU')

ph_gm_norm = ['gm_norm1.png','gm_norm2.png', 'gm_norm3.png', 'gm_norm4.png', 'gm_norm5.png']
ph_gm_ne_norm = ['gm_ne_norm1.png','gm_ne_norm2.png', 'gm_ne_norm3.png', 'gm_ne_norm4.png', 'gm_ne_norm5.png']
ph_night_norm = ['night_norm1.png','night_norm2.png', 'night_norm3.png', 'night_norm4.png', 'night_norm5.png']
ph_night_ne_norm = ['night_ne_norm1.png','night_ne_norm2.png', 'night_ne_norm3.png', 'night_ne_norm4.png', 'night_ne_norm5.png']
ph_have_norm = ['have_norm1.png','have_norm2.png', 'have_norm3.png', 'have_norm4.png', 'have_norm5.png']
ph_have_ne_norm = ['have_ne_norm1.png','have_ne_norm2.png', 'have_ne_norm3.png', 'have_ne_norm4.png', 'have_ne_norm5.png']
ph_hb = ['hb1.png','hb2.png', 'hb3.png', 'hb4.png', 'hb5.png','hb6.png', 'hb7.png', 'hb8.png']
ph_hol = ['hol1.png','hol2.png', 'hol3.png', 'hol4.png', 'hol5.png','hol6.png', 'hol7.png', 'hol8.png', 'hol9.png']
@bot.message_handler(commands = ['start'])
def main(message):# будет хранить всю информацию про чат
    bot.send_message(message.chat.id,f'Привет, {message.from_user.first_name}!❤️ \nЧтобы получить свою картинку, нужно выбрать повод.\n<u>Если хочешь пожелать</u>:\n<b>Доброго утра</b>, то введи /good_morning\n<b>Cпокойной ночи</b>, то введи /good_night\n<b>Хорошего дня</b>, то введи /have_a_nice_day\n<u>Если ты хочешь поздравить:</u>\n<b>С днем рождения</b>, то введи /happy_birthday\nС <b>несуществующим праздником</b>, то введи /holiday\n А если ты хочешь выйти, то просто нажми /exit.\nP.S. Не надо((\n P.S.S.. А также есть совсем неприличные картинки)))):\n Доброе утро - /good_morning_NOT\n Спокойной ночи - /good_night_NOT\n Хорошего дня - /have_a_nice_day_NOT', parse_mode='html')

@bot.message_handler(commands = ['good_morning'])
def main(message):
    photo = open(random.choice(ph_gm_norm), 'rb')
    bot.send_photo(message.chat.id, photo)

@bot.message_handler(commands = ['good_morning_NOT'])
def main(message):
    photo = open(random.choice(ph_gm_ne_norm), 'rb')
    bot.send_photo(message.chat.id, photo)

@bot.message_handler(commands = ['good_night'])
def main(message):
    photo = open(random.choice(ph_night_norm), 'rb')
    bot.send_photo(message.chat.id, photo)

@bot.message_handler(commands = ['good_night_NOT'])
def main(message):
    photo = open(random.choice(ph_night_ne_norm), 'rb')
    bot.send_photo(message.chat.id, photo)

@bot.message_handler(commands = ['have_a_nice_day'])
def main(message):
    photo = open(random.choice(ph_have_norm), 'rb')
    bot.send_photo(message.chat.id, photo)

@bot.message_handler(commands = ['have_a_nice_day_NOT'])
def main(message):
    photo = open(random.choice(ph_have_ne_norm), 'rb')
    bot.send_photo(message.chat.id, photo)

@bot.message_handler(commands = ['happy_birthday'])
def main(message):
    photo = open(random.choice(ph_hb), 'rb')
    bot.send_photo(message.chat.id, photo)

@bot.message_handler(commands = ['holiday'])
def main(message):
    photo = open(random.choice(ph_hol), 'rb')
    bot.send_photo(message.chat.id, photo)

@bot.message_handler(commands = ['exit'])
def main(message):
    bot.send_message(message.chat.id, 'Ну и все( ну и не надо(')



bot.polling(none_stop=True)
'''
![image](https://github.com/XenKov21/prob/assets/145853363/741ec83d-5a84-431f-940d-7a14cb8a674e)
