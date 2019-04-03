---
title: 암호 복잡성 (Visual Basic) 유효성 검사
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 829d6485acdca22fbf10160c734e5c7f931dd855
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824938"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="5b4d8-102">연습: 암호의 복합성 검사 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b4d8-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="5b4d8-103">이 메서드는 몇 가지 강력한 암호 특성에 대 한 확인 하 고 실패에 대 한 암호를 확인 하는 정보를 사용 하 여 문자열 매개 변수를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="5b4d8-104">사용자 권한을 부여 하는 보안 시스템에서 암호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="5b4d8-105">그러나 암호는 권한이 없는 사용자가 추측 하기 어려운 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="5b4d8-106">공격자가 사용할 수는 *사전 공격* 프로그램을 사전 (또는 다른 언어로 여러 사전)에 있는 단어의 모든 반복 하 고 사용자의 암호로 사용 된 단어 중 하나라도 있는지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="5b4d8-107">"양키스" 또는 "Mustang"와 같은 취약 한 암호를 신속 하 게 추측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="5b4d8-108">강력한 암호와 같은 "? 있습니다 'L1N3vaFiNdMeyeP@sSWerd! "를 추측할 수 될 가능성이 훨씬 적습니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="5b4d8-109">암호로 보호 된 시스템 사용자는 강력한 암호를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="5b4d8-110">강력한 암호 (대문자, 소문자, 숫자 및 특수 문자의 혼합 포함) 복잡 하며 단어 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="5b4d8-111">이 예제에서는 복잡성을 확인 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b4d8-112">예제</span><span class="sxs-lookup"><span data-stu-id="5b4d8-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="5b4d8-113">코드</span><span class="sxs-lookup"><span data-stu-id="5b4d8-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b4d8-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5b4d8-114">Compiling the Code</span></span>  
 <span data-ttu-id="5b4d8-115">해당 암호가 들어 있는 문자열을 전달 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="5b4d8-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-116">This example requires:</span></span>  
  
-   <span data-ttu-id="5b4d8-117"><xref:System.Text.RegularExpressions> 네임스페이스의 멤버에 대한 액세스 권한.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="5b4d8-118">코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="5b4d8-119">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="5b4d8-120">보안</span><span class="sxs-lookup"><span data-stu-id="5b4d8-120">Security</span></span>  
 <span data-ttu-id="5b4d8-121">를 사용 하는 네트워크를 통해 암호를 이동 하는 경우 데이터 전송에 안전한 방법을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="5b4d8-122">자세한 내용은 [ASP.NET 웹 응용 프로그램 보안](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="5b4d8-123">정확도 향상 시킬 수 있습니다는 `ValidatePassword` 복잡성 검사를 추가 하 여 함수:</span><span class="sxs-lookup"><span data-stu-id="5b4d8-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="5b4d8-124">암호 및 사용자의 이름과 사용자 id는 응용 프로그램 정의 사전 해당 부분 문자열을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="5b4d8-125">또한 비교를 수행할 때 동일한 것으로 시각적으로 유사한 문자를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="5b4d8-126">예를 들어 문자 "l" 및 "e" 숫자 "1" 및 "3"으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="5b4d8-127">대문자 하나만 있으면 암호의 첫 번째 문자 아닌지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="5b4d8-128">마지막 두 문자 암호의 문자 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="5b4d8-129">모든 기호는 키보드의 맨 위 행에서 입력 한 암호를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b4d8-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b4d8-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="5b4d8-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="5b4d8-131">[ASP.NET 웹 응용 프로그램 보안](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5b4d8-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
