---
title: '방법: Visual Basic에서 배열 정렬'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3f4dbd6dce0957de3451b1f29c3a67ccd6791045
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053667"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>방법: Visual Basic에서 배열 정렬
이 예제에서는 배열을 선언 `String` 명명 된 개체 `zooAnimals`, 채운 다음 사전순으로 정렬 합니다.  
  
## <a name="example"></a>예제  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- Mscorlib.dll에 대 한 액세스 및 <xref:System> 네임 스페이스입니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
- 배열이 비어 (<xref:System.ArgumentNullException> 클래스)  
  
- 배열이 다차원 (<xref:System.RankException> 클래스)  
  
- 배열의 하나 이상의 요소를 구현 하지 않는 합니다 <xref:System.IComparable> 인터페이스 (<xref:System.InvalidOperationException> 클래스)  
  
## <a name="see-also"></a>참고자료

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [배열 문제 해결](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [컬렉션](../../concepts/collections.md)
- [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
