## Deploy on VPS or PC.
- You need to Install git,ffmpeg,curl,nodejs,yarn with pm2 
   1. Install git ffmpeg curl 
      ``` 
       sudo apt -y update &&  sudo apt -y upgrade 
       sudo apt -y install git ffmpeg curl
      ``` 
   2. Install nodejs  
      ```   
      sudo apt -y remove nodejs
      curl -fsSl https://deb.nodesource.com/setup_lts.x | sudo bash - && sudo apt -y install nodejs
      ```
  
   3. Install yarn
      ```
      curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - 
      echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
      sudo apt -y update && sudo apt -y install yarn
      ```  
  
   4. Install pm2
      ```
      sudo yarn global add pm2
      ```
  
   5. Clone Repo and install required packages
      ```
      git clone https://github.com/Giftedmaurice/gifted-bot-md
      cd Gifted-Md
      yarn install --network-concurrency 1
      ```

   6. Create an env file for ENV. 
      ```
      touch config.env
      nano config.env
      ```
      copy paste lines below.

      ```
      OWNER_NUMBER="254728782591"
      SESSION_ID = "SESSION_22_35_02_23_eyJub2lzZUtleSI6eyJwcml2YXRlIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoibUNSRERYdDBLMFhGNTBkcW5tc3EzMFJlbXJQN0RUNkRHK0RSdHdOR0pFOD0ifSwicHVibGljIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoiNlJ0UGdTS01ib0lONU16Q1VmRnhjZmwxRGtyN25JTFhkMUdOQVcyNldCdz0ifX0sInBhaXJpbmdFcGhlbWVyYWxLZXlQYWlyIjp7InByaXZhdGUiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJhSVJibXNRS09CL1oxMkdzZEYxbHVqUXdOK2hLdU1NQ2x5SjVzVEY2QmtvPSJ9LCJwdWJsaWMiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJGZlpxcmlUWHZLN01XcWZ2UGZhZFhCamJmbVFrV0dDT1RpaU9oYlZoUG5nPSJ9fSwic2lnbmVkSWRlbnRpdHlLZXkiOnsicHJpdmF0ZSI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6Im1CUmhmK3FodnpBTDhJM0h1bmRpSUl5Tk8vVkRzQy9SV1VGNHZocndiSDA9In0sInB1YmxpYyI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6ImlQajczTjc0UHgvTFhlRm9wTW9NQUw0dDdvZnFtajhYTmo5VnhVZ0FZQjA9In19LCJzaWduZWRQcmVLZXkiOnsia2V5UGFpciI6eyJwcml2YXRlIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoic0xWS29BTjNUUzM2TzZpZDAvV24wVWhhdUUrOHZmZUcrWlM3b2QwZittST0ifSwicHVibGljIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoiYnFKcFIrWFZObnkwMStIVkxhN0o0d3RjVkxPWnhwOWh2dlB2Ylc2bEFURT0ifX0sInNpZ25hdHVyZSI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6IlhNYldNVTlCVHFOc3liNW42OW1Dbm5pSnZoc3ZJbFNIQ1dpcVRqcXdtV01IV2ZicTZ5N2NoTFFsMVY2TmtmaUg3ZkVXRTNJZ3pwMDRqR3k4dkNWVWlBPT0ifSwia2V5SWQiOjF9LCJyZWdpc3RyYXRpb25JZCI6MTEyLCJhZHZTZWNyZXRLZXkiOiJuOVdzczJOdUhuOHJ0aHlyVEJVcnhNTUkzaFlBMDZvSUs2MXB3bmZoaXk0PSIsInByb2Nlc3NlZEhpc3RvcnlNZXNzYWdlcyI6W3sia2V5Ijp7InJlbW90ZUppZCI6IjI1NDc0NjA5ODQ4NUBzLndoYXRzYXBwLm5ldCIsImZyb21NZSI6dHJ1ZSwiaWQiOiJEQThGMDlCOThBMjFBNzZBQTg4RkEwQjdCNjdCNTc3OCJ9LCJtZXNzYWdlVGltZXN0YW1wIjoxNzA4NzI3NzMyfSx7ImtleSI6eyJyZW1vdGVKaWQiOiIyNTQ3NDYwOTg0ODVAcy53aGF0c2FwcC5uZXQiLCJmcm9tTWUiOnRydWUsImlkIjoiNEZGODNBNjA5MDJBMUY2Q0U1NTU5NURFRTA3NTZFNUIifSwibWVzc2FnZVRpbWVzdGFtcCI6MTcwODcyNzczMn1dLCJuZXh0UHJlS2V5SWQiOjMxLCJmaXJzdFVudXBsb2FkZWRQcmVLZXlJZCI6MzEsImFjY291bnRTeW5jQ291bnRlciI6MSwiYWNjb3VudFNldHRpbmdzIjp7InVuYXJjaGl2ZUNoYXRzIjpmYWxzZX0sImRldmljZUlkIjoibWdxYmRrLTJTUHVaV0VDQ291RmNGdyIsInBob25lSWQiOiJjOTQyOGZhMi1hNGU2LTQ3MzAtYWE2ZC1iMTljNzI3MTA1MjciLCJpZGVudGl0eUlkIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoicDJ3SUdYSGx3MlJLb1cwaUFGeDVSTTA4MEFjPSJ9LCJyZWdpc3RlcmVkIjp0cnVlLCJiYWNrdXBUb2tlbiI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6InBDcDlDbWppSmxhRi9lU1RKT0hROHZZUG5oaz0ifSwicmVnaXN0cmF0aW9uIjp7fSwicGFpcmluZ0NvZGUiOiI0SDcxODdaTCIsIm1lIjp7ImlkIjoiMjU0NzQ2MDk4NDg1OjdAcy53aGF0c2FwcC5uZXQiLCJuYW1lIjoiUmVhbGVyIn0sImFjY291bnQiOnsiZGV0YWlscyI6IkNNSEh0OU1GRUt5NzVLNEdHQUVnQUNnQSIsImFjY291bnRTaWduYXR1cmVLZXkiOiJkY1Vta25rNFRMdW9mS2tXdHJNejlSY3RVZGxMRC8vQnNPdVEvY000VmpNPSIsImFjY291bnRTaWduYXR1cmUiOiJxWkJPQS9acWh3Ri81UjZLcjg4Z3VDaktmV3cwTDdxVjF6b0UxKzdNN3F0dzE4VGcxbklsMlpIK1BNTlh6YzZPakV3R3NSRktBZ25EU3NRczBrdXNBUT09IiwiZGV2aWNlU2lnbmF0dXJlIjoiNC9uNnJWTml6SFVNUTVWazFMSEF1SkFxN0ZvK20ybWpNd1RMQVRGVy93NnN0OW5qOTZzaG4wVDVoN1puV0JNUHhiSVlwTFlpeFIvbkorL3Rib2h2anc9PSJ9LCJzaWduYWxJZGVudGl0aWVzIjpbeyJpZGVudGlmaWVyIjp7Im5hbWUiOiIyNTQ3NDYwOTg0ODU6N0BzLndoYXRzYXBwLm5ldCIsImRldmljZUlkIjowfSwiaWRlbnRpZmllcktleSI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6IkJYWEZKcEo1T0V5N3FIeXBGcmF6TS9VWExWSFpTdy8vd2JEcmtQM0RPRll6In19XSwicGxhdGZvcm0iOiJzbWJhIiwibGFzdEFjY291bnRTeW5jVGltZXN0YW1wIjoxNzA4NzI3NzI4LCJteUFwcFN0YXRlS2V5SWQiOiJBQUFBQU5SWiJ9"
      THUMB_IMAGE = "https://telegra.ph/file/54efddccf41281ad7ec51.jpg"
      OWNER_NAME = "ɢɪғᴛᴇᴅ ᴛᴇᴄʜ"
      PREFIX = .
      WARN_COUNT = 5
      DISABLE_PM = "true"
      THEME= "GIFTED"
      MODE = "public"
      ANTILINK_VALUES = "https://,chat.whatsapp.com"
      
      ```
      ctrl + o and ctrl + x, To save and exit

   7. start and stop bot
 
      To start bot ``` npm start ```,
      To stop bot ``` npm stop ```

 
<h2 align="center">  NOTICE </h2>
---
- *Gifted-Md is not made by `WhatsApp Inc.` Sometimes or misusing the bot might `ban` your `WhatsApp account!`*
- *In that case, I'm not responsible for banning your account.*
- *Use Gifted-Md at your own risk by keeping this warning in mind.*
 
