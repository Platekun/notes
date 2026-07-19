# How Is The Size Of An Auto Scaling Group Decided?

Area: ASG (https://app.notion.com/p/ASG-d129a74129514f67894b3f3d03972614?pvs=21)
Reveal: No
Confidence: Not Confident
Answer: We have three metrics:
- The desired capacity which serves as the initial number of nodes of the system.
- The mininum capacity which is the minimum number of nodes needed by the system (after using policies).
- The maximum capacity which is the maximum number of nodes that AWS will let the ASG group grow to (after using policies).
Last edited time: February 15, 2023 1:58 AM