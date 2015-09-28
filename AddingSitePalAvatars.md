# Adding a SitePal Avatar #

You can add your own SitePal avatar to infoTabby. (It doesn't have to be a cat!) You'll need to make some changes to the custom .html files:

ivhost.html


```
<script language="JavaScript" type="text/javascript" src="http://vhost.oddcast.com/vhost_embed_functions.php?acc=*your SitePal account number*&js=1&followCursor=1"></script>
<script>
var vhostLoaded=false;
var vhostSpeaking=false;
 
function vh_sceneLoaded() {
  vhostLoaded=true;
}
function vh_talkEnded() {
  vhostSpeaking=false;
}
 
</script>
<table cellpadding="4" cellspacing="0" border="0">
 
<tr><td align="center">
<script language="JavaScript" type="text/javascript">
AC_VHost_Embed(*your SitePal account number*,345,460,'FFFFFF',1,1,*scenenumber*,0,0,0,'',9);
</script>
```

frame.html
<html>
<head><title>*Your bot name*</title>
<meta name="description" content="Famous Original ALICE bot created with AIML and hosted by Pandorabots"/>
<meta name="keywords" content="chatbot, chatterbot, chat bot, pandorabot, software robot, hosting, artificial intelligence, robot, AI, natural language, speech, voice, turing test, IM bot, NPC, game bot, Lisp, ALICE, A.L.I.C.E., Artificial Linguistic Internet Computer Entity"/>
</head>
<frameset rows="410,*">
<frame src="/pandora/talk?botid=*your PB bot ID*&skin=ivhost" name="vhost">
<frame src="/pandora/talk?botid=*your PB bot ID*&skin=input&speak=true" name="input">
</frameset>

input.html

{{{
<script language="javascript">
function sayit() {
  if (parent.vhost) {
>    if (parent.vhost.vhostLoaded) {
>      parent.vhost.vhostSpeaking=true;
>      Alert("sayText is called");
>      parent.vhost.sayText("<template context="tts"><response/></template>",1,1,3);
>
>    } else {
>      setTimeout("sayit()", 500);
>    }
>  }
> }
> sayit();
> </script>
}}}

The three numbers in {{{parent.vhost.sayText("<template context="tts"><response/></template>",1,1,3);}} determine which voice your avatar will use. SitePal has a list of codes to use to select the voice you wish. ```