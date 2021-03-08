---
ms.openlocfilehash: 5a027054024d8429831d73525ab3748c51ae850e
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255760"
---

패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다. 그러나, .NET Core를 수동으로 설치하거나 자체 포함된 앱을 게시할 경우 라이브러리가 설치되어 있는지 확인해야 합니다.

- krb5-libs
- libicu
- openssl-libs
- zlib

대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10** 을 설치해야 합니다.

종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.

*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.

- [libgdiplus(버전 6.0.1 이상)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > 시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다. 자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.
