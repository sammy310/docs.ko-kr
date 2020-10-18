---
title: 파일이 이미 열려 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162754"
---
# <a name="file-already-open"></a>파일이 이미 열려 있습니다.

경우에 따라 다른 작업을 수행 하거나 다른 작업을 수행 하기 전에 파일을 닫아야 합니다 `FileOpen` . 이 오류의 가능한 원인:

- `FileOpen`이미 열려 있는 파일에 대해 순차적 출력 모드 작업이 실행 되었습니다.

- 문이 열려 있는 파일을 참조 합니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 문을 실행 하기 전에 파일을 닫습니다.

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
