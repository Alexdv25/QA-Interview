1. Auto Scaling וזמינות גבוהה
יש לך אפליקציית וב (Web application) במצב Stateless, עם קפיצות בתעבורה (Traffic spikes) שמגיעות לפי 10 מקו הבסיס (Baseline). כיצד תתכנן ארכיטקטורת Auto Scaling כדי להתמודד עם זה ללא זמן השבתה (Zero downtime)?

2. EC2 Spot Instances וארכיטקטורת אצווה (Batch)
הסבר את ההבדל בין הפרעות של מופעי ספוט (EC2 Spot Interruptions) לבין סיום פעולת מופע ספוט (Spot Instance termination). כיצד תתכנן צינור עיבוד נתונים באצווה (Batch pipeline) העמיד בפני תקלות (Fault-tolerant) באמצעות Spot?

3. אופטימיזציה של AWS Lambda (מגבלות זמן)
פונקציית Lambda מגיעה למגבלת זמן הריצה (Timeout) של 15 דקות בזמן עיבוד של פילודים (Payloads) גדולים. פרט שלב אחר שלב את גישת התכנון מחדש (Redesign) שלך.

4. מחזור חיים של Lambda ו-Cold Starts
מהן ההשלכות של "התחלה קרה" (Cold start) על מחזור החיים של סביבת ההרצה (Execution environment lifecycle) של Lambda, וכיצד SnapStart שונה מ-Provisioned Concurrency?

5. רשתות וניתוב ב-AWS (זרם תעבורה)
הובל אותי במסלול שעושה בקשה (Request) מהדפדפן של המשתמש ועד לשירות ECS היושב בסאבנט פרטי (Private subnet). ציין כל רכיב AWS שבו היא נוגעת.

6. קישוריות רשת ב-VPC
הסבר את ההבדל בין VPC Peering, ל-AWS Transit Gateway ול-PrivateLink. מתי תבחר בכל אחד מהם?

7. latency ועלויות בין אזורי זמינות (Cross-AZ)
זמני התגובה (Latency) של האפליקציה שלך קופצים בעת תקשורת בין אזורי זמינות שונים (Availability Zones). כיצד תאבחן ותפחית את עלויות העברת הנתונים ואת ה-latency בין ה-AZs?

8. אסטרטגיית אחסון ומחזור חיים ב-S3
עליך לאחסן 500 TB של קובצי מדיה הנגישים בצורה אינטנסיבית במשך 30 יום לאחר העלאתם, ולאחר מכן לעיתים רחוקות בלבד. תכנן את מחזור החיים של S3 (S3 lifecycle) ואת אסטרטגיית אופטימיזציית העלויות.

9. מודל העקביות של S3
הסבר את מודל העקביות (Consistency model) של S3 לאחר עדכון העקביות החזקה (Strong consistency update) של שנת 2020, ומה המשמעות של כך עבור תכנון האפליקציה שלך כיום.

10. הבדלים בין שירותי אחסון (EFS vs EBS vs FSx)
מתי תבחר ב-EFS על פני EBS, ובאילו תנאים תעדיף את FSx for Lustre?

11. פתרון בעיות ב-DynamoDB
טבלת DynamoDB חווה בעיות של "פארטישן חם" (Hot partition issues). תאר את גורם השורש (Root cause) ושלוש אסטרטגיות לצמצום והקלות הבעיה (Mitigation strategies).

12. בסיסי נתונים גלובליים ואקטיביים
השווה בין Aurora Global Database לבין DynamoDB Global Tables עבור אפליקציה מבוזרת מרובת אזורים במצב אקטיבי-אקטיבי (Multi-region active-active). מהן הפשרות (Trade-offs) מבחינת עקביות הנתונים?

13. RDS Proxy וארכיטקטורת Serverless
הסבר מהו RDS Proxy ואילו בעיות ספציפיות הוא פותר עבור ארכיטקטורות המבוססות על Lambda.

14. אבטחה וניהול הרשאות (IAM)
הסבר את ההבדל בין IAM Roles, ל-Resource-based Policies ול-Permission Boundaries. כיצד הם משתלבים יחד כדי להעניק את הרשאות הקצה האפקטיביות (Final effective permissions)?

15. תגובה לאירועי אבטחה (Incident Response)
גילית שמפתח גישה של IAM (IAM access key) נחשף בריפו (Repository) ציבורי ב-GitHub. פרט שלב אחר שלב את תהליך התגובה שלך לאירוע (Incident response procedure).

16. הצפנה ב-AWS KMS
כיצד עובדת הצפנת מעטפת (Envelope encryption) ב-AWS KMS, ומתי תשתמש ב-CMK לעומת AWS Managed Keys לעומת Customer Managed Keys?

17. ארכיטקטורת אפס אמון (Zero-Trust)
תאר כיצד היית מיישם ארכיטקטורת רשת של "אפס אמון" (Zero-trust network architecture) עבור מיקרו-שירותים (Microservices) הרצים ב-ECS על גבי AWS.

18. תכנון מערכת בזמן אמת (Scale גבוה)
תכנן מערכת לזיהוי הונאות בזמן אמת (Real-time fraud detection) המעבדת 100,000 עסקאות בשנייה (TPS) ב-AWS.

19. דפוס עיצוב סאגה (Saga Pattern)
הסבר את דפוס הסאגה (Saga pattern) וכיצד היית מיישם אותו באמצעות AWS Step Functions כדי לשמור על עקביות הנתונים בין מיקרו-שירותים.

20. סקילביליות (Scaling) ומגבלותיה
מה ההבדל בין קנה מידה אופקי (Horizontal scaling) לקנה מידה אנכי (Vertical scaling) ב-AWS, ומהן המגבלות של כל אחד מהם?

21. מיגרציה ודפוס תאנת החנק (Strangler Fig Pattern)
יש להעביר מונוליט (Monolith) לארכיטקטורת מיקרו-שירותים ב-AWS. מהו דפוס "תאנת החנק" (Strangler Fig pattern) וכיצד מבצעים אותו ללא זמן השבתה (Zero downtime)?

22. ניהול עלויות (FinOps וחקירת חשבוניות)
חשבון ה-AWS שלך קפץ ב-40% מחודש לחודש. הובל אותי בתהליך החקירה ומתודולוגיית האופטימיזציה שלך.

23. מודלים של תמחור ב-EC2
הסבר את מסגרת קבלת ההחלטות לבחירה בין On-Demand, ל-Reserved Instances, ל-Savings Plans ול-Spot עבור עומס עבודה מעורב (Mixed workload).

24. עלויות העברת נתונים (Data Transfer)
כיצד עובדות עלויות העברת הנתונים (Data transfer costs) ב-AWS, ומהם דפוסי העלויות היקרים והנפוצים ביותר שצוותים נוטים לפספס?

25. הטמעת תרבות FinOps בארגון
התבקשת להטמיע פרקטיקות של FinOps עבור צוות הנדסה של 50 איש המשתמש ב-AWS Organizations. מה אתה בונה?

26. אסטרטגיות מיקום משימות ב-ECS
הסבר אסטרטגיות מיקום משימות (Task placement strategies) ואילוצים (Constraints) ב-ECS. כיצד תבטיח שהמשימות (Tasks) יתפזרו על פני מספר AZs ותמנע מעומס יתר על שרתים בודדים?

27. ניהול פריסות (Deployments) ו-ELB
מה קורה במהלך ביטול רישום של Load Balancer (הליך Elastic Load Balancer deregistration)? כיצד תמנע מניתוק בקשות (Dropped connections) במהלך פריסה (Deployment)?

28. מודל האחריות המשותפת (Shared Responsibility Model)
מהו מודל האחריות המשותפת של AWS וכיצד הוא משתנה בין שירותי IaaS (כמו EC2), שירותי PaaS (כמו RDS) ושירותי SaaS (כמו S3)?

29. תכנון בסיס נתונים ל-Latency נמוך ומספר משתמשים גבוה
אתה זקוק ל-Latency של פחות ממילי-שנייה (Sub-millisecond) עבור שאילתות טבלת מובילים (Leaderboard) באפליקציית משחקים עם 10 מיליון משתמשים. באילו מאגר נתונים (Data store) ומודל נתונים (Data model) תשתמש?

30. התאוששות מאסון (Disaster Recovery)
הסבר מהם RPO ו-RTO, והובל אותי דרך ארבעת דפוסי ההתאוששות מאסון (DR patterns) ב-AWS, מהזול ביותר ליקר ביותר.