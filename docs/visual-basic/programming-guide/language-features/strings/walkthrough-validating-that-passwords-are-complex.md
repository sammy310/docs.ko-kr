---
title: 암호 복잡도 확인
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 49e6f79c13c94a3f2f6891b259c4bb2bec54ae6f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344515"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="74049-102">연습: 암호의 복합성 검사(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74049-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="74049-103">이 메서드는 몇 가지 강력한 암호 특성을 확인 하 고 암호가 실패 한 검사에 대 한 정보를 사용 하 여 문자열 매개 변수를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="74049-104">암호는 보안 시스템에서 사용자에 게 권한을 부여 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74049-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="74049-105">그러나 암호는 권한이 없는 사용자가 추측 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74049-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="74049-106">공격자는 사전에 있는 모든 단어를 반복 하는 *사전 공격* 프로그램 (또는 다른 언어로 된 여러 사전을 사용 하 여)을 사용할 수 있으며, 모든 단어가 사용자의 암호로 작동 하는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="74049-107">"Yankees" 또는 "Mustang"와 같은 취약 한 암호를 신속 하 게 추측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74049-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="74049-108">더 강력한 암호 (예: "? 'L1N3vaFiNdMeyeP@sSWerd! "은 (는) 추측할 가능성이 훨씬 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="74049-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="74049-109">암호로 보호 된 시스템은 사용자가 강력한 암호를 선택 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="74049-110">강력한 암호는 복합 (대문자, 소문자, 숫자 및 특수 문자를 혼합 하 여) 하며 단어는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="74049-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="74049-111">이 예에서는 복잡성을 확인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74049-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74049-112">예</span><span class="sxs-lookup"><span data-stu-id="74049-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="74049-113">코드</span><span class="sxs-lookup"><span data-stu-id="74049-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="74049-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="74049-114">Compile the code</span></span>  
 <span data-ttu-id="74049-115">해당 암호를 포함 하는 문자열을 전달 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="74049-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-116">This example requires:</span></span>  
  
- <span data-ttu-id="74049-117"><xref:System.Text.RegularExpressions> 네임스페이스의 멤버에 대한 액세스 권한.</span><span class="sxs-lookup"><span data-stu-id="74049-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="74049-118">코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="74049-119">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74049-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="74049-120">보안</span><span class="sxs-lookup"><span data-stu-id="74049-120">Security</span></span>  
 <span data-ttu-id="74049-121">네트워크를 통해 암호를 이동 하는 경우 데이터를 전송 하는 안전한 방법을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="74049-122">자세한 내용은 [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74049-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="74049-123">더 복잡 한 검사를 추가 하 여 `ValidatePassword` 함수의 정확성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74049-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="74049-124">사용자 이름, 사용자 id 및 응용 프로그램 정의 사전과의 암호와 해당 부분 문자열을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="74049-125">또한 비교를 수행할 때 시각적으로 비슷한 문자를 동등 하 게 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="74049-126">예를 들어, "l" 및 "e" 문자를 숫자 "1"과 "3"에 해당 하는 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="74049-127">대문자가 하나만 있는 경우 암호의 첫 문자가 아닌지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="74049-128">암호의 마지막 두 문자가 편지 문자 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74049-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="74049-129">모든 기호가 키보드의 맨 위 행에서 입력 되는 암호를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74049-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74049-130">참조</span><span class="sxs-lookup"><span data-stu-id="74049-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="74049-131">[ASP.NET 웹 애플리케이션 보안](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="74049-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
