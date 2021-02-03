---
title: .NET SDK 개요
description: .NET 프로젝트를 만드는 데 사용되는 라이브러리 및 도구 집합인 .NET SDK에 대해 알아봅니다.
ms.date: 07/31/2019
ms.technology: dotnet-cli
ms.openlocfilehash: 5236d4abec5dcbf950059dd906958158cfb592fe
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216143"
---
# <a name="net-sdk-overview"></a>.NET SDK 개요

.NET SDK는 개발자가 .NET 애플리케이션과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다. 애플리케이션을 빌드하고 실행하는 데 사용되는 다음 구성 요소가 포함되어 있습니다.

- .NET CLI.
- .NET 라이브러리 및 런타임.
- `dotnet` [드라이버](tools/index.md#driver).

## <a name="acquiring-the-net-sdk"></a>.NET SDK 가져오기

모든 도구와 마찬가지로 먼저 컴퓨터에 도구를 가져와야 합니다. 시나리오에 따라 다음 방법 중 하나를 사용하여 SDK를 설치할 수 있습니다.

- 기본 설치 관리자를 사용합니다.
- 설치 셸 스크립트를 사용합니다.

기본 설치 관리자는 주로 개발자의 컴퓨터를 위한 것입니다. SDK는 Ubuntu의 DEB 패키지 또는 Windows의 MSI 번들 등 지원되는 플랫폼의 기본 설치 메커니즘을 사용하여 배포됩니다. 이러한 설치 관리자는 설치 후 SDK를 즉시 사용하려는 사용자에게 필요한 환경을 설치 및 설정합니다. 그러나 이러한 사용자는 컴퓨터에 대한 관리자 권한이 필요합니다. [.NET 다운로드](https://dotnet.microsoft.com/download) 페이지에 설치할 SDK를 찾을 수 있습니다.

반면 설치 스크립트는 관리 권한이 필요하지 않습니다. 그러나 머신에 필수 구성 요소도 설치되지 않습니다. 모든 필수 구성 요소를 수동으로 설치해야 합니다. 스크립트는 대개 빌드 서버를 설정하거나 관리자 권한 없이 도구를 설치할 경우 사용됩니다(위의 필수 구성 요소 주의 사항 참조). 자세한 내용은 [스크립트 참조 설치](tools/dotnet-install-script.md) 문서에서 확인할 수 있습니다. CI 빌드 서버에서 SDK를 설정하는 방법에 관심이 있는 경우 [CI(연속 통합)에서 .NET SDK 및 도구 사용](tools/using-ci-with-cli.md) 문서를 참조하세요.

기본적으로 SDK는 "side-by-side"(SxS) 방식으로 설치되므로 여러 버전이 단일 머신에서 동시에 공존할 수 있습니다. CLI 명령을 실행할 때 버전을 선택하는 방법은 [사용할 .NET 버전 선택](versions/selection.md) 문서에 자세히 설명되어 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET CLI 개요](tools/index.md)
- [.NET 버전 관리 개요](versions/index.md)
- [.NET 런타임 및 SDK를 제거하는 방법](install/remove-runtime-sdk-versions.md)
- [사용할 .NET 버전 선택](versions/selection.md)
