---
description: '자세한 정보: <exception> (Visual Basic)'
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 14b7f78dd2521f7d5b3d62f635baa5b50969afa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787476"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="aa298-102">\<exception>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa298-102">\<exception> (Visual Basic)</span></span>

<span data-ttu-id="aa298-103">Throw 할 수 있는 예외를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa298-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa298-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa298-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa298-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa298-105">Parameters</span></span>  

 `member`  
 <span data-ttu-id="aa298-106">현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="aa298-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="aa298-107">컴파일러는 지정된 예외가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa298-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="aa298-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa298-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="aa298-109">설명</span><span class="sxs-lookup"><span data-stu-id="aa298-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa298-110">설명</span><span class="sxs-lookup"><span data-stu-id="aa298-110">Remarks</span></span>  

 <span data-ttu-id="aa298-111">태그를 사용 `<exception>` 하 여 throw 할 수 있는 예외를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa298-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="aa298-112">이 태그는 메서드 정의에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa298-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="aa298-113">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="aa298-113">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa298-114">예제</span><span class="sxs-lookup"><span data-stu-id="aa298-114">Example</span></span>  

 <span data-ttu-id="aa298-115">이 예제에서는 태그를 사용 하 여 `<exception>` `IntDivide` 함수가 throw 할 수 있는 예외를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa298-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="aa298-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa298-116">See also</span></span>

- [<span data-ttu-id="aa298-117">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="aa298-117">XML Comment Tags</span></span>](index.md)
