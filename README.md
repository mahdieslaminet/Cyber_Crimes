# Cyber_Crimes
# نصب و ایمپورت ابزار های مورد نیاز
!pip install python-telegram-bot
from telegram import Update
from telegram.ext import Updater, CommandHandler, CallbackContext

# تابعی که بعد از دریافت دستور /start فعال می‌شود
def start(update: Update, context: CallbackContext) -> None:
    # ارسال پیام به کاربر که شامل ۶ گزینه است
    options = "لطفا یک گزینه را انتخاب کنید:\n"
    options += "1. عنوان اول\n"
    options += "2. عنوان دوم\n"
    options += "3. عنوان سوم\n"
    options += "4. عنوان چهارم\n"
    options += "5. عنوان پنجم\n"
    options += "6. عنوان ششم"
    
    update.message.reply_text(options)

def main() -> None:
# API Token را از پارامتر‌ها وارد کنید
    TOKEN = 'your_token_api'
    
    updater = Updater(TOKEN)
    
# اضافه کردن دستور /start به ربات
    updater.dispatcher.add_handler(CommandHandler('start', start))
    
# شروع دریافت پیام‌ها
    updater.start_polling()
    
# ربات باید فعال باشد تا زمانی که به صورت دستی خاموش شود
    updater.idle()

if __name__ == '__main__':
    main()



