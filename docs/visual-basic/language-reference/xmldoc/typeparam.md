---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 2ad54845645172acb5b91935f5347a828510e3aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411488"
---
# <a name="typeparam-visual-basic"></a>\<typeparam>(Visual Basic)
형식 매개 변수 이름 및 설명을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a>매개 변수  
 `name`  
 형식 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.  
  
 `description`  
 형식 매개 변수에 대 한 설명입니다.  
  
## <a name="remarks"></a>설명  
 `<typeparam>`제네릭 형식 또는 제네릭 멤버 선언에 대 한 주석의 태그를 사용 하 여 형식 매개 변수 중 하나를 설명 합니다.  
  
 [-Doc](../../reference/command-line-compiler/doc.md) 로 컴파일하여 문서 주석을 파일로 처리 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 태그를 사용 하 여 `<typeparam>` 매개 변수를 설명 합니다 `id` .  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](index.md)
