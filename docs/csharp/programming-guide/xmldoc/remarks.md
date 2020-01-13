---
title: <remarks> - C# 프로그래밍 가이드
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 2391a8ee0bb55402ff5183c837e36d04a39e6555
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711703"
---
# <a name="remarks-c-programming-guide"></a>\<remarks>(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>매개 변수  
 `Description`  
 멤버에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  
 \<remarks> 태그는 형식에 대한 정보를 추가하여 [\<summary>](./summary.md)로 지정된 정보를 보완하기 위해 사용됩니다. 이 정보는 개체 브라우저 창에 표시됩니다.  
  
 [-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
