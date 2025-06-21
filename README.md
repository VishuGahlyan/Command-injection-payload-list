# Command-injection-payload-list
Command injection ek attack hota hai jisme goal hota hai ki attacker arbitrary commands ko host operating system par execute karwa sake through ek vulnerable application. Command injection attacks tab possible hote hain jab koi application unsafe user supplied data (jaise forms, cookies, HTTP headers, etc.) ko system shell ko pass karta hai. Is attack mein, attacker ke diye hue operating system commands usually vulnerable application ke privileges ke saath execute hote hain. Command injection attacks mostly is wajah se hote hain kyunki input validation proper nahi hoti.

Yeh attack Code Injection se alag hota hai, kyunki code injection mein attacker apna khud ka code add karta hai jo application execute karta hai. Jabki command injection mein attacker application ki default functionality ko extend karta hai jo system commands ko execute karti hai, bina code inject kiye.

# What is OS command injection?
OS command injection ek bahut hi serious vulnerability hoti hai jo attackers ko affected website aur uske web server par poora control dilane ka moka deti hai.

OS command injection vulnerabilities tab hoti hain jab koi application user ka data lekar use operating system command mein include karti hai jo woh execute karti hai. Attacker is data ko manipulate karke apne khud ke commands run karwa sakta hai. Isse attacker wo sab kuch kar sakta hai jo application kar sakti hai, jaise uska sara data padhna ya modify karna, aur privileged actions perform karna.

Sirf web server ke poore compromise tak simit nahi, attacker command injection vulnerability ka use karke organization ke internal infrastructure par bhi attack kar sakta hai. Matlab, attacker web server ke access wale kisi bhi system tak pahunch sakta hai. Wo apne liye organization ke andar ek permanent foothold bhi bana sakta hai, jisse wo compromised systems tak lagataar access kar sakta hai, chahe asli vulnerability fix hi kyun na ho gayi ho.

# Description :
Operating system command injection vulnerabilities tab hoti hain jab koi application user ke control mein diye gaye data ko ek aise command mein use karti hai jo shell command interpreter ke through process hota hai. Agar user data ko sahi tarah validate na kiya jaye, toh attacker shell ke metacharacters ka use karke command ko modify kar sakta hai, aur apne arbitrary extra commands inject kar sakta hai jo server par execute ho jayenge.

OS command injection vulnerabilities usually bahut serious hoti hain aur server ko compromise karne ka reason ban sakti hain, chahe wo server jahan application host hai ya application ke data aur functionality. Kabhi-kabhi attacker server ko ek platform bana kar dusre systems par bhi attack kar sakta hai. Exploitation ka exact scope depend karta hai us security context par jisme command execute hoti hai, aur us context ke paas server ke sensitive resources par kya privileges hain.

# Remediation:
Jitna ho sake, applications ko user-controllable data ko operating system commands mein include karne se bachna chahiye. Almost har situation mein safer alternatives hote hain server-level tasks perform karne ke liye, jise manipulate karke extra commands nahi chalaye ja sakte jo intended nahi hain.

Agar phir bhi user-supplied data ko operating system commands mein include karna unavoidable ho, toh do layers of defense zaroor use karni chahiye attacks ko rokne ke liye:

User data ko strictly validate karna chahiye. Ideally, ek whitelist banani chahiye jisme sirf specific accepted values ho. Agar whitelist possible nahi, toh sirf chhoti alphanumeric strings accept karni chahiye. Aisi input jisme koi bhi shell metacharacter ya whitespace ho, use reject kar dena chahiye.

Application ko aise command APIs use karne chahiye jo specific process ko uske name aur command-line parameters ke through launch karte hain, na ki command string ko shell interpreter ko pass karte hain jisme command chaining aur redirection supported hota hai. Jaise, Java ka Runtime.exec aur ASP.NET ka Process.Start shell metacharacters ko support nahi karte. Yeh defense attacks ko kaafi had tak rok sakti hai.
