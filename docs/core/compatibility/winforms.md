---
title: Windows Forms 관련 호환성이 손상되는 변경 - .NET Core
description: .NET Core용 Windows Forms 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 11/27/2019
ms.openlocfilehash: 8fefa6e2f5a004e8bbe0e6e715f7fd467debb7a4
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567353"
---
# <a name="breaking-changes-in-windows-forms-net-core-to-net-core"></a>Windows Forms의 호환성이 손상되는 변경(.NET Core에서 .NET Core로 변경)

Windows Forms 지원이 버전 3.0의 .NET Core에 추가되었습니다. 이 문서에서는 Windows Forms의 호환성이 손상되는 변경 사항이 .NET Core 버전별로 표시됩니다. 이전 버전의 .NET Core(3.0 이상)에서 Windows Forms 앱을 업그레이드하는 경우 이 문서가 적용됩니다. Windows Forms 앱을 .NET Framework에서 .NET Core로 마이그레이션하는 경우 [Windows Forms의 호환성이 손상되는 변경(.NET Framework 에서 .NET Core로 변경)](../porting/winforms-breaking-changes.md)을 참조하세요.

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

## <a name="see-also"></a>참고 항목

- [Windows Forms의 호환성이 손상되는 변경(.NET Framework에서 .NET Core로 변경)](../porting/winforms-breaking-changes.md)
