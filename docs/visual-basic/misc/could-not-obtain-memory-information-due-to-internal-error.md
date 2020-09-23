---
title: 내부 오류 때문에 메모리 정보를 가져올 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_Memory
ms.assetid: 1ba8f774-5858-438e-914e-99fddc9e5e7e
ms.openlocfilehash: 550ac0345d54c8a78e805b224ffaba47a3970ea9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91076281"
---
# <a name="could-not-obtain-memory-information-due-to-internal-error"></a>내부 오류 때문에 메모리 정보를 가져올 수 없습니다.

`My.Computer.Info` 개체의 메모리 정보 속성 중 하나에 대한 호출이 실패했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `Try...Catch` 개체의 메모리 정보 속성에 대한 호출 주위에 `My.Computer.Info` 블록을 추가합니다.  
  
## <a name="see-also"></a>참조

- [My.Computer.Info](xref:Microsoft.VisualBasic.Devices.ComputerInfo)
- [Try ... Catch ... Finally 문](../language-reference/statements/try-catch-finally-statement.md)
