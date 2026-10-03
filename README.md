# ONE PIECE Unlimited World Red - Korean Patch

**원피스 언리미티드 월드 R 디럭스 에디션 한글패치**  
PC(Steam/Windows)판과 Nintendo Switch판을 지원합니다.

> 비공식 팬 한글패치입니다.  
> 게임 원본 파일은 포함하지 않으며, 패치 적용을 위해서는 정품 게임이 필요합니다.

---

## 지원 플랫폼

| PC / Steam / Windows | 
| Nintendo Switch | 
---

## 한글화 범위

- 메인 스토리 / 이벤트 / NPC 대사
- 메뉴 / 시스템 메시지
- 튜토리얼
- 퀘스트 / 스페셜 퀘스트
- 아이템 / 코스튬 관련 텍스트
- 낚시 / 곤충 채집 / 각종 결과창
- 대형 52x52 결과 폰트
- Break Rush 전용 커맨드 폰트
- 일부 UI 이미지
- 버튼 / D패드 / SELECT 표시 보정
- 4K UI 대응

Switch판은 Switch 전용 메시지와 튜토리얼도 별도로 반영되어 있습니다.

---

# PC판

## 설치 방법

1. 게임 파일이 가능한 한 **순정 상태**인지 확인합니다.
2. `OnePiece_UWR_KR_v1.0.exe`를 실행합니다.
3. ONE PIECE Unlimited World Red 게임 설치 폴더를 지정합니다.
4. 패치를 진행합니다.
5. 완료 후 게임을 실행합니다.

기존에 다른 모드나 파일 변경이 적용되어 있다면 설치에 실패하거나 일부 UI가 정상적으로 표시되지 않을 수 있습니다.

Steam의 **파일 무결성 검사** 또는 게임 업데이트를 실행하면 한글패치 파일이 원상복구될 수 있습니다. 이 경우 한글패치를 다시 적용해 주세요.

### PC판 주요 수정 사항

- 한국어 일반 폰트 적용
- 52x52 대형 결과 폰트 한글 대응
- 쵸파 땅파기 결과창 보정
- 아이템 획득 문장 어순 보정
- SELECT 버튼 표시 수정
- D패드 아이콘을 게임 원본 UI 스타일로 수정
- Break Rush 원본 입력 구조 복원
- Break Rush 동적 `Midair / Hold` 표시용 command font 한글 대응
- 1x / 4K UI 대응

---

# Nintendo Switch판

지원 Title ID:

```text
0100574002AF4000
```

## 준비물

- 본인이 소유한 게임에서 추출한 Switch판 데이터
- 최소한 아래 구조를 포함한 타이틀 덤프 폴더

```text
게임 덤프 폴더
└─ romfs
   ├─ rom0.cpk
   ├─ rom1.cpk
   ├─ rom2.cpk
   ├─ rom3.cpk
   ├─ rom4.cpk
   └─ rom7.cpk
```

패치툴은 `romfs\rom4.cpk`가 존재하는 폴더를 기준으로 원본을 확인합니다.

## 패치 생성 방법

1. `OnePiece_UWR_Switch_KR_PatchTool_V1.exe`를 실행합니다.
2. **Switch dump folder**에서 `romfs`가 들어 있는 타이틀 덤프 폴더를 선택합니다.
3. **Output parent folder**에서 결과물을 저장할 폴더를 선택합니다.
4. **Build Korean Patch**를 누릅니다.
5. 빌드가 끝나면 아래와 같은 LayeredFS 패키지가 생성됩니다.

```text
OnePieceUWR_Switch_Korean_Patch
└─ atmosphere
   └─ contents
      └─ 0100574002AF4000
         └─ romfs
```

## Switch 설치 방법

생성된 패키지의

```text
atmosphere
```

폴더를 **Switch SD카드 루트**에 복사합니다.

최종 경로는 다음과 같은 형태가 됩니다.

```text
SD카드
└─ atmosphere
   └─ contents
      └─ 0100574002AF4000
         └─ romfs
            ├─ rom0.cpk
            ├─ rom1.cpk
            ├─ rom2.cpk
            ├─ rom3.cpk
            ├─ rom4.cpk
            └─ rom7.cpk
```

Switch판은 **LayeredFS 방식**이며 PC판용 EXE 수정은 사용하지 않습니다.

### Switch판 전용 처리

- Switch 전용 main message 추가 대응
- Switch 전용 tutorial 10개 한글화
- Switch BNTX / BC4 block-linear 폰트 대응
- Switch 전용 swizzle / deswizzle 폰트 패처 사용
- Break Rush command font 한글 carrier 대응
- Switch 4K episode 이미지 별도 변환
- Switch 원본 버튼 아이콘 및 제어코드 유지
- Leader Change의 원본 `<icon 37>` 경로 유지
- PC판 전용 실행 파일 수정 및 PC 컨트롤러 텍스처 수정은 적용하지 않음

### Switch판 검증 상태

Switch V1은 정적/패키지 검증 기준으로 다음 항목을 통과했습니다.

- 번역 CSV **12,788행**
- 실질 미번역 **0행**
- main message 한국어 readback PASS
- Switch 전용 tutorial PASS
- 한글 carrier mapping PASS
- UI 이미지 적용 PASS
- 52x52 대형 폰트 PASS
- BNTX / BC4 기본 폰트 carrier PASS
- Break Rush command font PASS
- startup runtime static verify PASS
- costume / quest / special quest / DLC 관련 검증 PASS
- runtime semantic static verify **530개 PASS**
- Switch 네이티브 버튼 토큰 감사 PASS

단, 현재 배포 기준으로 **실제 Switch 또는 에뮬레이터에서의 최종 인게임 Runtime PASS는 별도 확인이 필요합니다.**

---

# 다운로드

최신 패치는 GitHub 저장소의 **Releases**에서 받을 수 있습니다.

PC판과 Switch판은 적용 방식이 다르므로 반드시 자신의 플랫폼에 맞는 파일을 받아 주세요.

---

# 문제 제보

문제가 발생하면 가능하면 아래 내용을 함께 남겨 주세요.

- 사용 플랫폼: PC / Switch
- 사용한 패치 버전
- 문제가 발생한 위치
- 재현 방법
- 스크린샷
- 패치툴에서 오류가 발생했다면 오류 로그

특히 UI나 특수 이벤트는 일반 대사와 다른 렌더링 경로를 사용하는 경우가 있어 스크린샷이 있으면 문제 확인에 큰 도움이 됩니다.

---

# 주의사항

- 본 패치는 비공식 팬 패치입니다.
- 게임 원본 데이터 및 저작권이 있는 게임 파일은 배포하지 않습니다.
- 반드시 본인이 소유한 게임을 사용해 주세요.
- 다른 모드와 함께 사용할 경우 충돌할 수 있습니다.
- 게임 업데이트 후에는 패치를 다시 적용해야 할 수 있습니다.
- Switch판은 PC판과 내부 파일 구조 및 폰트 구조가 다르므로 서로의 패치 파일을 혼용하지 마세요.

---

# 저작권

**ONE PIECE** 및 게임 관련 모든 권리는 각 원작자, 제작사 및 권리자에게 있습니다.

본 프로젝트는 비영리 목적의 비공식 한국어 패치입니다.

패치 파일의 무단 재배포, 출처를 제거한 재배포 또는 게임 원본 파일을 포함한 형태의 재배포는 삼가 주세요.

---
