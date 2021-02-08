---
description: "자세한 정보: BC30766: ' <functionname> '이 (가) 선언 되지 않았습니다 (스마트 장치/Visual Basic 컴파일러 오류)."
title: "'<functionname>'이 선언되지 않았습니다(스마트 디바이스-Visual Basic 컴파일러 오류)."
ms.date: 07/20/2015
f1_keywords:
- bc30766
- vbc30766
helpviewer_keywords:
- BC30766
ms.assetid: 13918600-6087-40d7-8134-32aa9d3bfda4
ms.openlocfilehash: 939af146656bc5e5e84b3f0672c730f6a816c043
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796160"
---
# <a name="bc30766-functionname-is-not-declared-smart-devicevisual-basic-compiler-error"></a>BC30766: ' \<functionname> '이 (가) 선언 되지 않았습니다 (스마트 장치/Visual Basic 컴파일러 오류).

<`functionname`> 선언 되지 않았습니다. 파일 I/O 기능은 일반적으로 `Microsoft.VisualBasic` 네임스페이스에서 사용할 수 있지만 대상 버전의 .NET Compact Framework에서 지원하지 않습니다.

 **오류 ID:** BC30766

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- `System.IO` 네임스페이스에 정의된 함수를 사용하여 파일 작업을 수행합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.IO>
- [Visual Basic을 사용한 파일 액세스](../../developing-apps/programming/drives-directories-files/file-access.md)
