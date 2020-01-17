---
title: Windows 8, Windows 8.1 또는 Windows 10에서 .NET Framework 1.1 앱 실행
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 507de3ca635986d1f4e0e3ba7c607a4af774cdcf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716271"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Windows 8, Windows 8.1 또는 Windows 10에서 .NET Framework 1.1 앱 실행

.NET Framework 1.1은 Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 또는 Windows 10 운영 체제에서 지원되지 않습니다. 앱을 실행하는 데 특별히 .NET Framework 1.1이 필요하다고 확인될 수도 있습니다. 이 경우 ISV(Independent Software Vendor)에 문의하여 .NET Framework 3.5 SP1 이상 버전에서 실행되도록 앱을 업그레이드해야 합니다. 자세한 내용은 [.NET Framework 1.1에서 마이그레이션](../migration-guide/migrating-from-the-net-framework-1-1.md)을 참조하세요.

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>CD 또는 다운로드 센터에서 .NET Framework 1.1 설치

.NET Framework 1.1을 Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 또는 Windows 10에 수동으로 설치할 수는 없습니다. 더 이상 지원되지 않습니다. 패키지를 설치하려고 하면 다음 오류 메시지가 표시됩니다. "이 버전의 .NET Framework가 이전에 설치된 버전과 호환되지 않기 때문에 설치를 계속 할 수 없습니다." 이 문제를 해결하려면 [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22)을 설치합니다. 이 버전에는 Windows 8, Windows 8.1 및 Windows 10.에서 지원되는 .NET Framework 2.0(.NET Framework 1.1 후속 릴리스)이 포함되어 있습니다. 항상 먼저 앱을 설치하여 .NET Framework의 이후 버전으로 자동으로 업데이트되는지 확인해야 합니다. 그러지 않으면 ISV에 앱 업데이트에 대해 문의하세요.

## <a name="see-also"></a>참조

- [.NET Framework 1.1에서 마이그레이션](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치](dotnet-35-windows-10.md)
