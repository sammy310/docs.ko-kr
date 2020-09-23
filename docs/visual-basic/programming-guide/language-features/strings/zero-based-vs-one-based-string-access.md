---
title: 0부터 시작하는 문자열 액세스 및 1부터 시작하는 문자열 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 91d3fb9d7bfdf3d5af27fc6499583640946a802f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072290"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Visual Basic에서 0부터 시작하는 문자열 액세스와 1부터 시작하는 문자열 액세스 비교

이 항목에서는 Visual Basic 및 .NET Framework에서 문자열의 문자에 대 한 액세스를 제공 하는 방법을 비교 합니다. .NET Framework는 항상 문자열의 문자에 대 한 0부터 시작 하는 액세스를 제공 하는 반면 Visual Basic는 함수에 따라 0부터 시작 하는 액세스와 1부터 시작 하는 액세스를 제공 합니다.  
  
## <a name="one-based"></a>1부터  

 1부터 Visual Basic 함수를 사용 하는 방법에 대 한 예는 함수를 참조 `Mid` 하세요. 위치 1부터 시작 하 여 부분 문자열이 시작 되는 문자 위치를 나타내는 인수를 사용 합니다. .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 위치 0부터 시작 하 여 부분 문자열이 시작 될 문자열의 문자 인덱스를 사용 합니다. 따라서 "ABCDE...Z" 문자열을 사용 하는 경우 개별 문자는 함수와 함께 사용 하기 위해 1, 2, 3, 4, 5로 번호가 매겨집니다 `Mid` . 하지만 메서드와 함께 사용할 경우에는 0, 1, 2, 3, 4입니다 <xref:System.String.Substring%2A?displayProperty=nameWithType> .  
  
## <a name="zero-based"></a>0부터 시작  

 0부터 시작 하는 Visual Basic 함수의 예는 함수를 참조 `Split` 하세요. 문자열을 분할 하 고 부분 문자열을 포함 하는 배열을 반환 합니다. 또한 .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> 메서드는 문자열을 분할 하 고 부분 문자열을 포함 하는 배열을 반환 합니다. `Split`함수 및 메서드는 <xref:System.String.Split%2A> .NET Framework 배열을 반환 하기 때문에 0부터 시작 해야 합니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Visual Basic의 문자열 소개](introduction-to-strings.md)
