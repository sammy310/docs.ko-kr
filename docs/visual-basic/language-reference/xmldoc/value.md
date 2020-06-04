---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411475"
---
# <a name="value-visual-basic"></a>\<value>(Visual Basic)
속성에 대 한 설명을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>매개 변수  
 `property-description`  
 속성에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  
 태그를 사용 `<value>` 하 여 속성을 설명 합니다. Visual Studio 개발 환경에서 코드 마법사를 사용 하 여 속성을 추가 하면 [\<summary>](summary.md) 새 속성의 태그가 추가 됩니다. 그런 다음 `<value>` 속성이 나타내는 값을 설명 하는 태그를 수동으로 추가 해야 합니다.  
  
 [-Doc](../../reference/command-line-compiler/doc.md) 로 컴파일하여 문서 주석을 파일로 처리 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 태그를 사용 하 여 `<value>` 속성에 포함 된 값을 설명 합니다 `Counter` .  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](index.md)
