---
title: <exception> - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 4e4204996c006ce6e943c9a09661001b0e0c2a14
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523465"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="b0e48-102">\<exception>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b0e48-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b0e48-103">구문</span><span class="sxs-lookup"><span data-stu-id="b0e48-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0e48-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0e48-104">Parameters</span></span>  
 <span data-ttu-id="b0e48-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="b0e48-105">cref = " `member`"</span></span>  
 <span data-ttu-id="b0e48-106">현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e48-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="b0e48-107">컴파일러는 지정된 예외가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e48-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="b0e48-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e48-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="b0e48-109">제네릭 형식을 참조하도록 `member` 형식을 지정하는 방법에 대한 자세한 내용은 [XML 파일 처리](processing-the-xml-file.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0e48-109">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>
  
 `description`  
 <span data-ttu-id="b0e48-110">예외에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b0e48-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0e48-111">설명</span><span class="sxs-lookup"><span data-stu-id="b0e48-111">Remarks</span></span>  
 <span data-ttu-id="b0e48-112">\<exception> 태그를 사용하면 throw할 수 있는 예외를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e48-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="b0e48-113">이 태그는 메서드, 속성, 이벤트 및 인덱서에 대한 정의에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0e48-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="b0e48-114">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b0e48-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="b0e48-115">예외 처리에 대한 자세한 내용은 [예외 및 예외 처리](../exceptions/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0e48-115">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0e48-116">예</span><span class="sxs-lookup"><span data-stu-id="b0e48-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b0e48-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0e48-117">See also</span></span>

- [<span data-ttu-id="b0e48-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b0e48-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b0e48-119">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="b0e48-119">Recommended Tags for Documentation Comments</span></span>](recommended-tags-for-documentation-comments.md)
