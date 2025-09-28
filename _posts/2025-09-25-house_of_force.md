---
layout: post
title: House Of Force
date: 2025-09-25 17:20:00 +0900 
categories: ["glibc", "exploit", "heap"]
tags: ["glibc", "exploit", "heap"]
---
# House Of Fore

## 1. Top Chunk
  
Top Chunk는 힙이 초기화 될 때 만들어지는 Chunk로써 일반적인 Chunk와 달리 Free, Allocate란 상태로 관리되지 않는다. Top Chunk는 Bin 혹은 Tcache에서 꺼내줄 해제된 적당한 chunk가 없을 때 Top Chunk를 일부 쪼개 할당해주고, 나머지는 다시 Top Chunk가 된다. Top Chunk 또한 다른 Chunk와 마찬가지로 Size 필드가 존재하며, 이를 통해 남아 있는 Top Chunk의 크기를 확인 할 수 있다. 일반적으로 Top Chunk의 크기를 넘어서는 할당 요청은 sbrk 혹은 mmap 요청을 통해 할당을 처리한다. 만약 어떤 방식으로든지 Top Chunk의 Size 필드를 조작할 수 있게 된다면, 이번에 설명할 House Of Force란 exploit을 트리거할 수 있게 된다.  
  
## 2. Exploit
  




