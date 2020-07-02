---
ms.openlocfilehash: 416590c7bd959eea011b7e7c5db48f22d349d0f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615660"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>SHA-256 코드 서명 인증서를 사용하는 ClickOnce로 게시된 앱이 Windows 2003에서 실패할 수 있음

#### <a name="details"></a>설명

실행 파일이 SHA256으로 서명됩니다. 이전에는 코드 서명 인증서가 SHA-1 또는 SHA-256인지에 관계없이 SHA1로 서명되었습니다. 적용 대상:

- Visual Studio 2012 이상으로 빌드된 모든 애플리케이션
- .NET Framework 4.5가 있는 시스템에서 Visual Studio 2010 또는 이전 버전으로 빌드된 애플리케이션
또한 .NET Framework 4.5 이상이 있는 경우 컴파일 시의 대상 .NET Framework 버전에 관계없이 ClickOnce 매니페스트도 SHA-256 인증서에 대해 SHA-256으로 서명됩니다.

#### <a name="suggestion"></a>제안 해결 방법

ClickOnce 실행 파일의 서명 변경 내용은 Windows Server 2003 시스템에만 영향을 줍니다. KB 938397을 설치해야 합니다. 앱이 .NET Framework 4.0 또는 이전 버전을 대상으로 하는 경우에도 SHA-256으로 매니페스트에 서명하는 변경 내용으로 인해 .NET Framework 4.5 이상 버전에서 런타임 종속성이 발생합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.5         |
| 형식    | 대상 변경 |
