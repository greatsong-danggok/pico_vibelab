# Pico VIBE.LAB

**당곡고 × 수도여고 「인공지능과 피지컬 컴퓨팅」**

손바닥만 한 라즈베리파이 피코 보드 하나로 빛을 만들고, 공기를 측정하고, 실시간으로 데이터를 그래프로 띄워보는 프로젝트 모음입니다.

> **AI proposes, humans decide.**

## 🌐 사이트 바로가기

👉 `https://<your-github-id>.github.io/<repo-name>/`

## 📚 프로젝트

| # | 제목 | 만들 것 |
|---|---|---|
| **01** | LED 한 개로 만드는 나만의 빛 작품 | 무지개·심장박동·사이렌·호흡 표현 |
| **02** | 공기를 측정해서 웹 대시보드로 보기 | 가스 센서 + Wi-Fi 실시간 모니터링 |

## 🛠 준비물

- Raspberry Pi Pico 2 WH (MicroPython 설치)
- WS2813 Mini NeoPixel (Lesson 01)
- MQ-2 가스 센서 (Lesson 02)
- Thonny IDE
- Wi-Fi 환경 (Lesson 02)

## 📁 파일 구조

```
.
├── index.html              # 메인 페이지 (프로젝트 목록)
├── lesson01_led.html       # Lesson 01 · LED 빛 작품
├── lesson02_mq2.html       # Lesson 02 · 가스 센서 대시보드
└── README.md
```

각 HTML은 외부 의존성 없이 그대로 브라우저에서 열립니다 (CDN으로 폰트·Prism만 로드).

## ✏️ 프로젝트 추가하기

1. `lesson02_mq2.html`을 복사 (컴포넌트가 가장 다양함)
2. 파일명 `lessonNN_topic.html`
3. 사이드바 `nav`, 본문 `section`, 푸터 수정
4. `index.html`에 카드 추가

## 🤝 함께 쓰는 분들께

이 자료는 수업용으로 만들었지만, 다른 학교·다른 동아리에서도 자유롭게 가져다 쓰셔도 됩니다. 학교명 부분만 본인 환경에 맞게 바꾸시면 됩니다.

---

© 2026 석리송 · 당곡고 × 수도여고 인공지능과 피지컬 컴퓨팅
