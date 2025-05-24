## ১. PostgreSQL কি?

PostgreSQL হলো একটা অবজেক্ট-রিলেশনাল ডাটাবেস ম্যানেজমেন্ট সিস্টেম (ORDBMS) যা ওপেন সোর্স আর ফ্রি! এইটা ১৯৮৬ সালে ইউনিভার্সিটি অফ ক্যালেফোর্নিয়াতে প্রফেসর মাইকেল স্টোনব্রেকার আর তার টিমের দ্বারা ডেভেলপ করা হয়েছিল। PostgreSQL অন্য ডাটাবেসগুলার চেয়ে অনেক বেশি ফিচার রিচ। এইটা শুধু রিলেশনাল ডাটাবেস না, এইটা অবজেক্ট-রিলেশনাল। মানে আপনি এইখানে কাস্টম ডাটা টাইপ বানাইতে পারবেন, এমনকি JSON ডাটাও স্টোর করতে পারবেন।

### PostgreSQL কেন অন্য relational database গুলার চেয়ে আলাদা?

Object-oriented features গুলা কি কি? PostgreSQL এর object-oriented features দিয়ে programmers পারে database servers এর সাথে objects ব্যবহার করে communicate করতে, complex custom data types define করতে, নিজেদের data types এর জন্য functions define করতে, আর tables এর মধ্যে inheritance বা parent-child relationships define করতে। এইসব ফিচার গুলা PostgreSQL কে অন্য relational database গুলার থেকে আলাদা করে।

এইটার মানে হইলো PostgreSQL এর ডিজাইন অন্য relational database এর চেয়ে অনেক বেশি flexible। আপনি existing database system এর ভিতরেই different relationships আর types model করতে পারবেন, আপনার এপ্লিকেশন কোডে externally করতে হবে না। Database performance improve হয় আর consistency maintain হয় কারণ intended behavior actual data এর কাছেই enforce করা হয়।

PostgreSQL আসলে একটা enterprise-grade সলিউশন যেটা ছোট স্টার্টআপ থেকে শুরু করে বড় কর্পোরেশন পর্যন্ত সবাই ব্যবহার করতে পারে। এর flexibility, robustness, আর community support এর কারণে এটা মডার্ন এপ্লিকেশনের জন্য দারুণ চয়েস!

## ২. PostgreSQL এ ডাটাবেস স্কিমার কাজ কি?

ডাটাবেস স্কিমা হলো আসলে একটা লজিক্যাল কন্টেইনার যেটা আমাদের ডাটাবেস অবজেক্টগুলাকে অরগানাইজ করে রাখে। এইটাকে একটা ফোল্ডার সিস্টেমের মত ভাবতে পারেন যেখানে আলাদা আলাদা ক্যাটাগরির জিনিস আলাদা ফোল্ডারে রাখা হয়।

একটা PostgreSQL ডাটাবেসের ভিতরে অনেকগুলা স্কিমা থাকতে পারে। ডিফল্ট স্কিমা হলো 'public' কিন্তু আপনি এখানে যতখুশি কাস্টম স্কিমা বানাইতে পারবেন। এইটার সবচেয়ে বড় সুবিধা হলো namespace separation। মানে আপনি একই নামের টেবিল আলাদা আলাদা স্কিমায় রাখতে পারবেন।

ধরেন আপনার একটা বড় e-commerce অ্যাপ্লিকেশন আছে। আপনি এইভাবে স্কিমা ভাগ করতে পারেন:

- `inventory` স্কিমায় products, categories, stock_levels টেবিল
- `customer` স্কিমায় users, addresses, preferences টেবিল
- `sales` স্কিমায় orders, payments, invoices টেবিল
- `analytics` স্কিমায় reports, metrics টেবিল

এইভাবে কোড অনেক ক্লিন থাকে। ডেভেলপারদের আলাদা আলাদা স্কিমায় পারমিশন দিতে পারেন। যেমন analytics টিমকে শুধু analytics স্কিমার রিড পারমিশন দিয়ে রাখতে পারেন।
