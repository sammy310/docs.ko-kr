---
title: <param> - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: ed7a8f8a06771a18dc4244bffbda53e9adbd4e90
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523423"
---
# <a name="param-c-programming-guide"></a>\<param>(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a>매개 변수  
 `name`  
 메서드 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.  
  
 `description`  
 매개 변수에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  
 \<param> 태그는 메서드의 매개 변수 중 하나를 설명하기 위해 메서드 선언에 대한 주석에 사용해야 합니다. 여러 매개 변수를 문서화하려면 여러 개의 \<param> 태그를 사용합니다.  
  
 \<param> 태그에 대한 텍스트는 IntelliSense, 개체 브라우저 및 코드 주석 웹 보고서에 표시됩니다.  
  
 [-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
