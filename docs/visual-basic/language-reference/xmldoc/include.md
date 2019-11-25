---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 2f2bebfd06d4614f05cb66834cc5bef40524ce3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348453"
---
# <a name="include-visual-basic"></a><span data-ttu-id="a624c-101">\<include> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a624c-101">\<include> (Visual Basic)</span></span>
<span data-ttu-id="a624c-102">Refers to another file that describes the types and members in your source code.</span><span class="sxs-lookup"><span data-stu-id="a624c-102">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a624c-103">구문</span><span class="sxs-lookup"><span data-stu-id="a624c-103">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="a624c-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a624c-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="a624c-105">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a624c-105">Required.</span></span> <span data-ttu-id="a624c-106">문서가 포함된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a624c-106">The name of the file containing the documentation.</span></span> <span data-ttu-id="a624c-107">경로를 사용하여 파일 이름을 정규화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a624c-107">The file name can be qualified with a path.</span></span> <span data-ttu-id="a624c-108">Enclose `filename` in double quotation marks (" ").</span><span class="sxs-lookup"><span data-stu-id="a624c-108">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="a624c-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a624c-109">Required.</span></span> <span data-ttu-id="a624c-110">`filename`의 태그 경로로, `name` 태그에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a624c-110">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="a624c-111">Enclose the path in double quotation marks (" ").</span><span class="sxs-lookup"><span data-stu-id="a624c-111">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="a624c-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a624c-112">Required.</span></span> <span data-ttu-id="a624c-113">The name specifier in the tag that precedes the comments.</span><span class="sxs-lookup"><span data-stu-id="a624c-113">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="a624c-114">`Name` will have an `id`.</span><span class="sxs-lookup"><span data-stu-id="a624c-114">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="a624c-115">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a624c-115">Required.</span></span> <span data-ttu-id="a624c-116">주석 앞에 오는 태그의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a624c-116">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="a624c-117">Enclose the ID in single quotation marks (' ').</span><span class="sxs-lookup"><span data-stu-id="a624c-117">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a624c-118">주의</span><span class="sxs-lookup"><span data-stu-id="a624c-118">Remarks</span></span>  
 <span data-ttu-id="a624c-119">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span><span class="sxs-lookup"><span data-stu-id="a624c-119">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="a624c-120">소스 코드 파일에 직접 문서 주석을 포함하는 대신 사용되는 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="a624c-120">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="a624c-121">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span><span class="sxs-lookup"><span data-stu-id="a624c-121">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="a624c-122">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span><span class="sxs-lookup"><span data-stu-id="a624c-122">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a624c-123">예제</span><span class="sxs-lookup"><span data-stu-id="a624c-123">Example</span></span>  
 <span data-ttu-id="a624c-124">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="a624c-124">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="a624c-125">The format of the `commentFile.xml` is as follows.</span><span class="sxs-lookup"><span data-stu-id="a624c-125">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a624c-126">참조</span><span class="sxs-lookup"><span data-stu-id="a624c-126">See also</span></span>

- [<span data-ttu-id="a624c-127">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="a624c-127">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
