---
title: <inheritdoc> - C# 프로그래밍 가이드
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 6f42462f21d045428577cd2123e2180d866f1e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156950"
---
# <a name="inheritdoc-c-programming-guide"></a>\<inheritdoc>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a>InheritDoc

기본 클래스, 인터페이스 및 유사한 메서드에서 XML 주석을 상속합니다. 이렇게 하면 중복 XML 주석을 복사하여 붙여 넣을 필요가 없으며 XML 주석이 자동으로 동기화됩니다.
  
## <a name="remarks"></a>설명  
기본 클래스 또는 인터페이스에 XML 주석을 추가하고 InheritDoc가 주석을 구현 클래스에 복사하도록 합니다.

동기 메서드에 XML 주석을 추가하고 InheritDoc가 동일한 메서드의 비동기 버전에 주석을 복사하도록 합니다.  

특정 멤버에서 주석을 복사하려면 `cref` 특성을 사용하여 멤버를 지정할 수 있습니다.
  
## <a name="examples"></a>예
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
