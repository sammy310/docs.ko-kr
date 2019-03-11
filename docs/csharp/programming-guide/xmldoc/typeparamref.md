---
title: <typeparamref> - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: a9b0b9dec09e891105336b3cf0088ed279386d13
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471929"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="2b695-102">\<typeparamref>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="2b695-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2b695-103">구문</span><span class="sxs-lookup"><span data-stu-id="2b695-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b695-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b695-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="2b695-105">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2b695-105">The name of the type parameter.</span></span> <span data-ttu-id="2b695-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="2b695-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b695-107">주의</span><span class="sxs-lookup"><span data-stu-id="2b695-107">Remarks</span></span>  
 <span data-ttu-id="2b695-108">제네릭 형식 및 메서드의 형식 매개 변수에 대한 자세한 내용은 [제네릭](../../../csharp/programming-guide/generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b695-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="2b695-109">이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b695-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="2b695-110">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2b695-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b695-111">예제</span><span class="sxs-lookup"><span data-stu-id="2b695-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="2b695-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b695-112">See also</span></span>

- [<span data-ttu-id="2b695-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2b695-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2b695-114">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="2b695-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
