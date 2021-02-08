---
description: "자세한 정보: BC30830: ' Line ' 문은 더 이상 지원 되지 않습니다."
title: "'Line' 문은 더 이상 지원되지 않습니다(Visual Basic 컴파일러 오류)."
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 16696856cee365171000e7b0abc206c42d3f3174
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795874"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a>BC30830: ' Line ' 문은 더 이상 지원 되지 않습니다.

줄 문은 더 이상 지원 되지 않습니다. 파일 i/o 기능은로 제공 되며 `Microsoft.VisualBasic.FileSystem.LineInput` 그래픽 기능은로 사용할 수 있습니다 `System.Drawing.Graphics.DrawLine` .

 **오류 ID:** BC30830

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 파일 액세스를 수행 하는 경우를 사용 `Microsoft.VisualBasic.FileSystem.LineInput` 합니다.

- 그래픽을 수행하는 경우 `System.Drawing.Graphics.Drawline`을 사용합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.IO>
- <xref:System.Drawing>
- [Visual Basic을 사용한 파일 액세스](../../developing-apps/programming/drives-directories-files/file-access.md)
