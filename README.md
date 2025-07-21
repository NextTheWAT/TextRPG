# 🧙‍♂️ TextRPG - 콘솔 기반 C# 텍스트 RPG

콘솔에서 즐기는 고전 RPG 스타일 게임!  
직업을 선택하고, 다양한 몬스터와 전투를 벌이며 퀘스트를 클리어해보세요.
---

## 🎮 주요 기능

- ✅ 직업 선택 (전사 / 마법사 / 궁수 / 도적 / 해적)
- ✅ 고유 스킬 사용 및 MP 소모
- ✅ 전투 시스템 (일반 공격, 스킬 공격)
- ✅ 던전 난이도 선택 및 실패 확률
- ✅ 레벨업 및 능력치 성장
- ✅ 상점에서 아이템 구매/판매
- ✅ 인벤토리 및 장착 시스템
- ✅ 퀘스트 수락 및 완료
- ✅ 게임 저장 및 불러오기 (다중 슬롯)
---

## 🛠 기술 스택

| 분류 | 내용 |
|------|------|
| 언어 | C# (.NET Console App) |
| 패턴 | OOP (상속, 다형성, 인터페이스) |
| 자료구조 | List, Dictionary, LINQ |
| 구조화 | 클래스 분리, 모듈화, 책임 분산 |
---

## 🚀 실행 방법

1. Visual Studio로 `TextRPG.sln` 열기
2. `Program.cs` 실행 (또는 Ctrl + F5)
3. 콘솔에서 지시에 따라 플레이 진행
---

## 🚀 GIF
![Text_RPG](https://github.com/user-attachments/assets/e6dddef7-eb3b-44ce-b8a2-c9f12f42ad8a)


🚀 TroubleShooting
1️⃣ 직업 클래스 분리의 한계와 구조 개선
<p align="center"> <img src="https://github.com/user-attachments/assets/47808fec-57a5-4cbb-a315-e8c7c9c67962" width="48%"> <img src="https://github.com/user-attachments/assets/6ee050ce-3498-4b37-a7f8-f5291f270163" width="48%"> </p>
초기에는 직업마다 클래스를 따로 정의하여 능력치와 스킬을 관리했으나,
중복 코드가 많고 확장성이 떨어졌으며, 유지보수도 어려웠다.
개선을 통해 Job을 문자열 필드로 단순화하고, SkillSet 인터페이스 기반으로 구조를 개선하였다.

2️⃣ 퀘스트 클래스 세분화
<p align="center"> <img src="https://github.com/user-attachments/assets/8aa3e594-541b-4c16-bd03-502d9ce9cd33" width="48%"> <img src="https://github.com/user-attachments/assets/85f85828-4dd9-4979-8859-9a65baea2f8c" width="48%"> </p>
초기에는 단일 Quest 클래스에서 모든 데이터를 처리했기 때문에
조건 검사, UI 출력, 보상 처리 로직이 혼재되어 관리가 복잡했다.
이를 Quest / QuestUI / QuestManager로 분리하여 책임을 분산하고 구조를 단순화했다.

3️⃣ 재귀 호출: 상태 기반 전투 흐름의 구조적 개선
<p align="center"> <img src="https://github.com/user-attachments/assets/bd198891-316d-4176-b7db-0a1430df3677" width="48%"> <img src="https://github.com/user-attachments/assets/37396ca3-c291-4fc1-985c-916b05b8d98f" width="48%"> </p>
전투 흐름을 메서드 내부에서 다른 메서드를 직접 호출하는 재귀 구조로 설계해
반복 전투 시 스택이 계속 쌓이는 문제가 있었다.
이를 enum BattleState와 while-switch 구조로 변경하여 안정적인 상태 전이 구조를 갖추었다.

4️⃣ 전투 체력 추적 구조 개선: a = b, b = c, c = a
<p align="center"> <img src="https://github.com/user-attachments/assets/bb036cc4-371a-4469-b714-e9b67ef8f1d6" width="48%"> <img src="https://github.com/user-attachments/assets/a52db704-e1c6-47e2-9e70-c082bc6ffc41" width="48%"> </p>
전투 결과에서 체력 변화가 명확하게 표시되지 않는 문제가 있었고,
체력 데이터를 일관성 있게 추적하기 위해 a=b, b=c, c=a 방식으로 분리 저장/출력 구조를 개선했다.
이를 통해 전투 시작, 중간, 종료 시 체력 변화를 직관적으로 표현할 수 있었다.

5️⃣ 아이템 효과 구조의 한계
<p align="center"> <img src="https://github.com/user-attachments/assets/991755ea-41c7-4745-b09e-0ec7b18899b5" width="48%"> <img src="https://github.com/user-attachments/assets/e4c29080-0ec2-4c67-aaea-17ee77ef84a7" width="48%"> </p>
기존에는 아이템 효과를 클래스 내 개별 변수로 선언해
새로운 효과 추가 시 코드 수정이 필수였고,
하나의 아이템이 복수의 효과를 가지는 데에 한계가 있었다.
이를 배열 기반으로 설계하여 아이템 효과를 동적으로 처리하고, 확장성과 재사용성을 높였다.




