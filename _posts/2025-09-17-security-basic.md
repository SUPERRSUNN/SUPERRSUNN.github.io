---
layout: post
title: "Basic Security Tech"
date: 2025-09-17 13:25:00 +0900
categories: ["sec_tech","exploit"]
tags: ["PIE","RELRO", "ASLR", "NX", "Canary"]
---
## Basic Binary Protection & exploit 

1. ASLR (Address Space Layout Randomization)
2. NX (No Execute)
3. Canary
4. PIE (Position Indepent Execute)
5. RELRO (Relocation Read-Only)





### 1. ASLR

ASLR은Linux Kernel 수준에서 적용하는 보호 기법으로, 임의의 바이너리가 실행되기 위해 매핑될 때 Stack, Heap, Lib, Data, BSS와 같은 영역의 Base를 무작위로 바꾸는 보호 기법을 의미한다. 이 때문에 대부분의 익스플로잇 상황에서는 Lib Leak 혹은 Stack, Data 영역의 Base를 알아내야 한다.

### 2. NX 

NX 또한 커널이 적용하는 보호 기법으로, 실행 명령어를 제외한 모든 부분에서 실행 권한을 없애는 기법이다. 즉 바이너리가 매핑 될 때 명령어로 쓰여진 부분만 실행 할 수 있고, 그 이외의 데이터는 명령어로 간주하지 않는 것이다. 해당 기능은 Linux Kernel의 vm_area_struct를 살펴보면 알 수 있다. 

### 3. Canary
### 4. PIE
### 5. RELRO 
