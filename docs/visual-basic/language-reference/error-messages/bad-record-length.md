---
title: 레코드 길이가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 6967015572b2567f52697f7ddcb1ff594013a2c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869259"
---
# <a name="bad-record-length"></a>레코드 길이가 잘못되었습니다.

이 오류의 가능한 원인:  
  
- , 또는 문에 지정 된 record 변수의 길이가 `FileGet` `FileGetObject` `FilePut` `FilePutObject` 해당 문에 지정 된 길이와 다릅니다 `FileOpen` .  
  
- `FilePut`또는 `FilePutObject` 문의 변수가 이거나 가변 길이 문자열을 포함 하는 경우  
  
- 또는의 변수가 `FilePut` `FilePutObject` 이거나 `Variant` 형식을 포함 하는 경우  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. Record 변수의 형식을 정의 하는 사용자 정의 형식에서 고정 길이 변수 크기의 합이 문의 절에 지정 된 값과 동일한 지 확인 합니다 `FileOpen` `Len` .  
  
2. `FilePut`또는 문의 변수가 또는 `FilePutObject` 가변 길이 문자열을 포함 하는 경우 가변 길이 문자열이 문의 절에 지정 된 레코드 길이 보다 2 자 이상 길어야 합니다 `Len` `FileOpen` .  
  
3. 또는의 변수가 이거나를 포함 하는 경우 `FilePut` `FilePutObject` `Variant` 가변 길이 문자열이 문의 절에 지정 된 레코드 길이 보다 4 바이트 이상 길어야 합니다 `Len` `FileOpen` .  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
