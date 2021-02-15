---
description: '자세한 정보: 내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.'
title: 내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: d274a08728b084b21309862de69e2fded5c164da
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463496"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.

내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다. 이는 현재 컴퓨터에 존재하지 않는 WMI에 의해 발생할 수 있습니다.  
  
 `My.Computer.Info.OSFullName` 속성 호출이 실패했습니다. 현재 컴퓨터에 WMI(Windows Management Instrumentation)가 설치되지 않아서 이 오류가 발생했을 수 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. `Try...Catch` 속성을 호출하는 주변에 `My.Computer.Info.OSFullName` 블록을 추가합니다.  
  
2. WMI 및 설치 방법에 대 한 자세한 내용을 보려면로 이동 하 여 "WMI(Windows Management Instrumentation) Core"를 검색 하십시오.  
  
## <a name="see-also"></a>추가 정보

- [My.computer. Svfullname](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [.NET의 예외 처리 및 Throw](../../standard/exceptions/index.md)
- [Try...Catch...Finally 문](../language-reference/statements/try-catch-finally-statement.md)
