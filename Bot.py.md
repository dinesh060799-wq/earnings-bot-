import logging  
from telegram import Bot, InlineKeyboardButton, InlineKeyboardMarkup  
  
# Logging setup  
logging.basicConfig(format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', level=logging.INFO)  
  
# Bot Configuration (Directly filled from your details)  
TOKEN = "9109171463:AAFKcy-coEC8CNowDvDN..."  
CHANNEL_NAME = "@BullStockspro"  
  
bot = Bot(token=TOKEN)  
  
def send_test_alert():  
    message_text = "✨ **Bot Connected Successfully!**✨\nआपका अर्निंग्स ऑटोमेशन बॉट `@BullStockspro` पर एक्टिव हो गया है।"  
      
    keyboard = [  
        [  
            InlineKeyboardButton("Result ↗", url="https://www.tradingview.com"),  
            InlineKeyboardButton("Chart ↗", url="https://www.tradingview.com")  
        ]  
    ]  
    reply_markup = InlineKeyboardMarkup(keyboard)  
      
    try:  
        # Replace CHANNEL_NAME with your chat_id or channel username if sending to channel  
        bot.send_message(  
            chat_id=CHANNEL_NAME,  
            text=message_text,  
            parse_mode="Markdown",  
            reply_markup=reply_markup  
        )  
        print("Alert sent successfully!")  
    except Exception as e:  
        print(f"Error sending message: {e}")  
  
if __name__ == "__main__":  
    send_test_alert()  
