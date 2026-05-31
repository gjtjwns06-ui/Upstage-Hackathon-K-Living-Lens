# 🏥 K-Living Lens : 의료·행정 토탈 라이프케어 AI 어시스턴트

![Upstage](https://img.shields.io/badge/Upstage-Solar_LLM-blue)
![n8n](https://img.shields.io/badge/n8n-Workflow_Automation-EA4B71)
![Status](https://img.shields.io/badge/Status-Hackathon_Project-success)

**K-Living Lens**는 복잡한 의료 영수증과 관공서 공문서를 AI로 분석하여 외국인, 고령자 등 정보 취약계층의 행정·의료 장벽을 허무는 맞춤형 AI 솔루션입니다. 

---

## 🎥 시연 영상 (Video)
[![K-Living Lens 데모 영상](https://img.youtube.com/vi/c6aekLLJW3c/0.jpg)](https://www.youtube.com/watch?v=c6aekLLJW3c)


> 👆 이미지를 클릭하시면 AI 전화 브리핑 등 상세 작동 영상을 확인하실 수 있습니다.

## 🌟 핵심 기능 (Key Features)

1. **AI 의료 문서 분석 및 다국어 맞춤 요약**
   * 복잡한 진료비 세부내역서 및 영수증 이미지를 업로드하면 핵심 정보를 자동 추출하고 번역합니다.
2. **안전한 개인정보 보안 처리 (마스킹)**
   * AI 분석 전, 문서 내 주민등록번호, 이름 등 민감한 개인정보를 식별하고 비식별화하여 데이터 유출을 원천 차단합니다.
3. **스마트 할 일(Checklist) 및 캘린더 연동**
   * 서류 제출 기한, 다음 병원 방문일 등을 파악하여 구글 캘린더에 자동으로 일정을 등록합니다.
4. **위치 정보 시각화 및 긴급 AI 전화 문의**
   * 문서에 기재된 병원/약국 주소를 구글 지도로 즉시 매핑합니다.
   * 언어 장벽 해소를 위해 AI 에이전트가 해당 기관에 직접 전화를 걸어 필요한 절차를 대신 문의하고 브리핑합니다.

---

## ⚙️ 기술 스택 및 아키텍처 (Tech Stack)
<img width="2463" height="1169" alt="스크린샷 2026-05-30 210348" src="https://github.com/user-attachments/assets/d6ec93cb-0246-460b-bfdb-e0b94424ce9f" />

본 프로젝트의 백엔드 파이프라인은 **n8n**을 기반으로 완벽하게 모듈화(Decoupling)되어 설계되었습니다.

* **Upstage Document Parse API**: 복합 OCR 전처리를 통해 복잡한 영수증 이미지의 레이아웃을 손실 없이 고정밀 텍스트로 변환.
* **Upstage Information Extract API**: 개인정보(PII) 식별 및 보안 마킹 
* **Upstage Solar LLM**: 텍스트화된 문서를 분석, 다국어 요약, 중요도 판별 및 행동 가이드(JSON) 생성.
* **Google Maps & Calendar API**: 사용자 맞춤 동선 매핑 및 일정 자동 등록.
* **AI Call Agent**: AI 음성 브리핑 및 자동 발신(Outbound) 처리.

---

## 🛠️ 활용 방법 (How to use)

본 레포지토리에 포함된 `workflow.json` 파일을 통해 n8n 환경에서 즉시 파이프라인을 재현할 수 있습니다.

1. [n8n](https://n8n.io/) 인스턴스를 실행합니다.
2. 새 워크플로우를 생성한 뒤, 화면에 `workflow.json` 파일을 드래그 앤 드롭(Import)합니다.
3. 각 노드에 필요한 API Key (Upstage, Google 등)를 Credentials에 등록합니다.
4. 프론트엔드 UI(Lovable 등)에서 생성된 Webhook URL로 POST 요청을 보내 테스트합니다.

---

## 🚀 확장성 및 비전 (Scalability)

K-Living Lens는 단순한 기술 데모를 넘어 무한한 수평적 확장이 가능하도록 설계되었습니다.
* **[금융]** 추출된 의료 데이터를 통한 실손보험 원클릭 다이렉트 자동 청구
* **[약국]** AI가 모국어로 알려주는 복약 지도 및 투약 시간 안심 콜
* **[공공/행정]** B2G 연계를 통한 다문화 가정/외국인 관공서 행정 대리 문의 서비스

---

## 🧑‍💻 개발자 (Developer)
* **Heo Seo-jun (허서준)**
