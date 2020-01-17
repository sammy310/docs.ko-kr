---
title: 호환성이 손상되는 변경 사항 - .NET Framework에서 .NET Core로 변경
description: .NET Framework에서 .NET Core로의 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 12/18/2019
ms.openlocfilehash: 5c29636664632e80e4235e922a3296c34fdbef36
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900130"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a>.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 변경 사항

.NET Framework에서 .NET Core로 마이그레이션하는 경우, 다음 문서에 표시된 호환성이 손상되는 변경 사항이 영향을 줄 수 있습니다. 호환성이 손상되는 변경 사항은 범주별로 그룹화됩니다.

> [!NOTE]
> 이 문서는 .NET Framework와 .NET Core 간 호환성이 손상되는 변경 사항의 전체 목록이 아닙니다. 가장 중요한 호환성이 손상되는 변경 사항은 이를 인식하는 대로 여기에 추가됩니다.

## <a name="corefx"></a>CoreFx

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

## <a name="windows-forms"></a>Windows Forms

Windows Forms 앱을 .NET Framework에서 .NET Core 3.0 이상으로 마이그레이션하는 경우의 호환성이 손상되는 변경 사항에 대한 자세한 내용은 [Windows Forms의 호환성이 손상되는 변경 사항(.NET Framework에서 .NET Core로 변경)](../porting/winforms-breaking-changes.md)을 참조하세요.

## <a name="see-also"></a>참조

- [.NET Core에서 항상 예외를 throw하는 API](unsupported-apis.md)
- [.NET Core에서 사용할 수 없는 .NET Framework 기술](../porting/net-framework-tech-unavailable.md)
