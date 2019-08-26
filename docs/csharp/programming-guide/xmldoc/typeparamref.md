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
ms.openlocfilehash: f01df27b920dcf3011a51015c771d2da3b442c4c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587423"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="8ef06-102">\<typeparamref>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8ef06-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8ef06-103">구문</span><span class="sxs-lookup"><span data-stu-id="8ef06-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ef06-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ef06-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8ef06-105">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ef06-105">The name of the type parameter.</span></span> <span data-ttu-id="8ef06-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="8ef06-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ef06-107">설명</span><span class="sxs-lookup"><span data-stu-id="8ef06-107">Remarks</span></span>  
 <span data-ttu-id="8ef06-108">제네릭 형식 및 메서드의 형식 매개 변수에 대한 자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ef06-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="8ef06-109">이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ef06-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="8ef06-110">[/doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef06-110">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ef06-111">예</span><span class="sxs-lookup"><span data-stu-id="8ef06-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="8ef06-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ef06-112">See also</span></span>

- [<span data-ttu-id="8ef06-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8ef06-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8ef06-114">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="8ef06-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
