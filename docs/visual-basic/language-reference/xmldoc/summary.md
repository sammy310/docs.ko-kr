---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 471d3ddb5cf5a234cb77de6d1d93309faf754359
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865835"
---
# <a name="summary-visual-basic"></a>\<summary>(Visual Basic)

멤버의 요약을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>매개 변수  

 `description`  
 개체에 대한 요약입니다.  
  
## <a name="remarks"></a>설명  

 태그를 사용 `<summary>` 하 여 형식 또는 형식 멤버를 설명 합니다. [\<remarks>](remarks.md)를 사용하여 형식 설명에 보충 정보를 추가할 수 있습니다.  
  
 태그에 대 한 텍스트는 `<summary>` IntelliSense의 형식에 대 한 유일한 정보 소스 이며 개체 브라우저에도 표시 됩니다. 개체 브라우저에 대 한 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조 하세요.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 태그를 사용 하 여 `<summary>` `ResetCounter` 메서드 및 `Counter` 속성을 설명 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](index.md)
