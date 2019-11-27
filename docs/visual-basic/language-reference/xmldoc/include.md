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
# <a name="include-visual-basic"></a><span data-ttu-id="97c63-101">\<> (Visual Basic) 포함</span><span class="sxs-lookup"><span data-stu-id="97c63-101">\<include> (Visual Basic)</span></span>
<span data-ttu-id="97c63-102">소스 코드의 형식 및 멤버를 설명 하는 다른 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-102">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c63-103">구문</span><span class="sxs-lookup"><span data-stu-id="97c63-103">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="97c63-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97c63-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="97c63-105">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-105">Required.</span></span> <span data-ttu-id="97c63-106">문서가 포함된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-106">The name of the file containing the documentation.</span></span> <span data-ttu-id="97c63-107">경로를 사용하여 파일 이름을 정규화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-107">The file name can be qualified with a path.</span></span> <span data-ttu-id="97c63-108">`filename`를 큰따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-108">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="97c63-109">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-109">Required.</span></span> <span data-ttu-id="97c63-110">`filename`의 태그 경로로, `name` 태그에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-110">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="97c63-111">경로를 큰따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-111">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="97c63-112">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-112">Required.</span></span> <span data-ttu-id="97c63-113">주석 앞에 오는 태그의 이름 지정자입니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-113">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="97c63-114">`Name`에는 `id`있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-114">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="97c63-115">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-115">Required.</span></span> <span data-ttu-id="97c63-116">주석 앞에 오는 태그의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-116">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="97c63-117">ID를 작은따옴표 (' ')로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-117">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97c63-118">주의</span><span class="sxs-lookup"><span data-stu-id="97c63-118">Remarks</span></span>  
 <span data-ttu-id="97c63-119">`<include>` 태그를 사용 하 여 소스 코드의 형식 및 멤버를 설명 하는 다른 파일의 주석을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-119">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="97c63-120">소스 코드 파일에 직접 문서 주석을 포함하는 대신 사용되는 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-120">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="97c63-121">`<include>` 태그는 W3C XPath (XML Path Language) 버전 1.0 권장 사항을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-121">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="97c63-122">`<include>` 사용을 사용자 지정 하는 방법에 대 한 자세한 내용은 <https://www.w3.org/TR/xpath>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97c63-122">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97c63-123">예제</span><span class="sxs-lookup"><span data-stu-id="97c63-123">Example</span></span>  
 <span data-ttu-id="97c63-124">이 예제에서는 `<include>` 태그를 사용 하 여 `commentFile.xml`이라는 파일에서 멤버 문서 주석을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-124">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="97c63-125">`commentFile.xml` 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97c63-125">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97c63-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97c63-126">See also</span></span>

- [<span data-ttu-id="97c63-127">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="97c63-127">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
