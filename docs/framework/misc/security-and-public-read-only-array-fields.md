---
title: 보안 및 공용 읽기 전용 배열 필드
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 215e8136b4bc3f2982cdb2d8382b0eca6a881f9b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217043"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="9ee95-102">보안 및 공용 읽기 전용 배열 필드</span><span class="sxs-lookup"><span data-stu-id="9ee95-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="9ee95-103">읽기 전용 공용 배열 필드를 수정할 수 있으므로 관리 되는 라이브러리의 읽기 전용 공용 배열 필드를 사용 하 여 응용 프로그램의 경계 동작 또는 보안을 정의 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9ee95-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ee95-104">설명</span><span class="sxs-lookup"><span data-stu-id="9ee95-104">Remarks</span></span>  
 <span data-ttu-id="9ee95-105">일부 .NET framework 클래스에는 플랫폼별 경계 매개 변수를 포함 하는 읽기 전용 public 필드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="9ee95-106">예를 들어 <xref:System.IO.Path.InvalidPathChars> 필드는 파일 경로 문자열에 허용 되지 않는 문자를 설명 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="9ee95-107">많은 유사한 필드가 .NET Framework 전체에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="9ee95-108"><xref:System.IO.Path.InvalidPathChars>와 같은 공용 읽기 전용 필드의 값은 코드 또는 코드의 응용 프로그램 도메인을 공유 하는 코드로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="9ee95-109">응용 프로그램의 경계 동작을 정의 하려면 다음과 같은 읽기 전용 공용 배열 필드를 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="9ee95-110">이렇게 하면 악의적인 코드가 경계 정의를 변경 하 고 코드를 예기치 않은 방식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="9ee95-111">.NET Framework 버전 2.0 이상에서는 공용 배열 필드를 사용 하는 대신 새 배열을 반환 하는 메서드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="9ee95-112">예를 들어 <xref:System.IO.Path.InvalidPathChars> 필드를 사용 하는 대신 <xref:System.IO.Path.GetInvalidPathChars%2A> 메서드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="9ee95-113">.NET Framework 형식은 공용 필드를 사용 하 여 내부적으로 경계 형식을 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="9ee95-114">대신 .NET Framework 별도의 전용 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="9ee95-115">이러한 공용 필드의 값을 변경 해도 .NET Framework 형식의 동작은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee95-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee95-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ee95-116">See also</span></span>

- [<span data-ttu-id="9ee95-117">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="9ee95-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
