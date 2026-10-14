# HarvestIQ — uburyo bwo gushyiraho urubuga nyakuri

Urubuga rufite indimi 4: English (EN), Kinyarwanda (RW), Kiswahili (SW), Français (FR).
Harimo ibice bya Garlic Farming Intelligence na AfriAvo Intelligence, login/sign up/reset UI, dashboard, profile, referrals, billing UI, security UI.

## Icyo ugomba kumenya
- Dosiye ya HTML yonyine ntabwo ihita ikora konti nyakuri. Ukeneye umushinga wa Supabase, hanyuma ugashyira URL na anon/public key muri `CONFIG` muri `index.html`.
- Login, sign up, email verification, reset password na change password bikoresha Supabase Auth nyuma yo gushyiraho ayo makuru no kwemeza email settings.
- SMS OTP ntirashyirwamo: igomba guhuza SMS provider no gushyiraho amafaranga/credentials zayo.
- Payment ntabwo ifungura checkout cyangwa ngo ifate amafaranga. Ntushyireho payment nyakuri utarahitamo provider, uhujije backend/checkout/webhook kandi ukagerageza payment muri test mode. Ntukoreshe secret key muri HTML.
- Referral code igaragara mu dashboard ni code y'uwinjiye; kubika referrals n'ibihembo bisaba backend rules n'ikizamini kirinda kwibeshya/uburiganya.
- Hindura `hello@harvestiq.example` uyisimbuze email yawe nyakuri.

## Intambwe zo gukora
1. Fungura supabase.com, kora project nshya, ubike database password yawe ahantu hizewe.
2. Muri Supabase > SQL Editor, shyiramo `supabase_setup.sql` yose uyikoreshe (Run).
3. Muri Supabase > Authentication > URL Configuration, shyiraho URL y'urubuga rwawe. Shyiraho Site URL na redirect URLs zo kuri domain uzacapishaho.
4. Muri Authentication > Providers, fasha Email. Shyiraho SMTP provider niba ushaka email zizewe ku bantu benshi. Koresha email confirmation.
5. Muri Project Settings > API, fata Project URL na anon/public key (ntabwo ari service_role secret).
6. Fungura `index.html`, shaka `const CONFIG={...}` hafi y'intangiriro ya JavaScript, ushyiremo URL na anon key byawe. Ntushyiremo service_role key.
7. Shyira `index.html` kuri hosting ya HTTPS (urugero Netlify, Cloudflare Pages, cyangwa GitHub Pages). Kuri static hosting, backend iba Supabase.
8. Gerageza sign up ukoresheje email yawe, wemeze email, winjire, usohoke, usabe password reset, uhindure password. Gerageza mobile na desktop.
9. Mbere yo kwakira amafaranga, hitamo payment provider ikorera Rwanda, wubake server-side checkout + verified webhook, kandi ukoreshe test mode. UI y'ubu ntifata amafaranga.

## Ubufasha
Ntugashyire passwords, SMTP secrets, service_role key cyangwa payment secret keys muri GitHub cyangwa muri HTML. Koresha environment secrets za hosting/serverless functions.
