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

## 🚀 트러블슈팅

<p align="center">
  <img src="https://github.com/user-attachments/assets/47808fec-57a5-4cbb-a315-e8c7c9c67962" width="48%">
  <img src="https://github.com/user-attachments/assets/6ee050ce-3498-4b37-a7f8-f5291f270163" width="48%">
</p>

> 장착 아이템 능력치가 저장/불러오기 시 반영되지 않는 문제를 해결한 과정입니다.  
> 플레이어 상태만 저장하고 장비 효과는 저장하지 않아 발생한 문제였고, 불러올 때 장착 장비 효과를 재적용하도록 수정하여 해결했습니다.











