---
title: Windows 8, Windows 8.1 또는 Windows 10에서 .NET Framework 1.1 앱 실행
description: 여러 버전의 Windows 운영 체제에서 더 이상 지원되지 않는 .NET Framework 1.1이 필요한 앱을 수용하는 방법을 설명합니다.
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 6d1cb2f9251bba96d0a378bf4dbab9f7da267037
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111792"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Windows 8, Windows 8.1 또는 Windows 10에서 .NET Framework 1.1 앱 실행

.NET Framework 1.1은 Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 또는 Windows 10 운영 체제에서 지원되지 않습니다. 경우에 따라 애플리케이션을 실행하려면 .NET Framework 1.1이 필요합니다. 이 경우 개별 소프트웨어 공급업체(ISV)에 문의하여 .NET Framework 3.5 SP1 이상 버전에서 실행되도록 앱을 업그레이드해야 합니다. 자세한 내용은 [.NET Framework 1.1에서 마이그레이션](../migration-guide/migrating-from-the-net-framework-1-1.md)을 참조하세요.

## <a name="install-net-framework-11-from-a-cd-or-download-center"></a>CD 또는 다운로드 센터에서 .NET Framework 1.1 설치

.NET Framework 1.1을 CD 또는 다운로드 센터에서 수동으로 Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 또는 Windows 10에 설치할 수는 없습니다. 더 이상 지원되지 않습니다. 패키지를 설치하려고 하면 다음 오류 메시지가 표시됩니다. "이 버전의 .NET Framework가 이전에 설치된 버전과 호환되지 않기 때문에 설치를 계속 할 수 없습니다." 이 문제를 해결하려면 [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22)을 설치합니다. 이 버전에는 Windows 8, Windows 8.1 및 Windows 10.에서 지원되는 .NET Framework 2.0(.NET Framework 1.1 후속 릴리스)이 포함되어 있습니다. 항상 먼저 앱을 설치하여 .NET Framework의 이후 버전으로 자동으로 업데이트되는지 확인해야 합니다. 그렇지 않으면 ISV에 앱 업데이트에 대해 문의하세요.

## <a name="see-also"></a>참조

- [.NET Framework 1.1에서 마이그레이션](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치](dotnet-35-windows-10.md)
