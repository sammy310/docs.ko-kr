---
title: 사용자 데이터 액세스(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- domain names [Visual Basic], retrieving
- data [Visual Basic], accessing user data
- My.User object [Visual Basic], tasks
- user data [Visual Basic], domain
- user names [Visual Basic], retrieving
- user data [Visual Basic], accessing
- login names [Visual Basic]
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
ms.openlocfilehash: e5d18adcb331162a72da0adb4018d1d59ecc072e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825302"
---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="16c7d-102">사용자 데이터 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16c7d-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="16c7d-103">이 섹션에는 `My.User` 개체 및 이 개체로 수행할 수 있는 작업을 설명하는 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16c7d-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="16c7d-104">`My.User` 개체는 <xref:System.Security.Principal.IPrincipal> 인터페이스를 구현하는 개체를 반환하여 로그온한 사용자 정보에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16c7d-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="16c7d-105">작업</span><span class="sxs-lookup"><span data-stu-id="16c7d-105">Tasks</span></span>  
  
|<span data-ttu-id="16c7d-106">대상</span><span class="sxs-lookup"><span data-stu-id="16c7d-106">To</span></span>|<span data-ttu-id="16c7d-107">참조</span><span class="sxs-lookup"><span data-stu-id="16c7d-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="16c7d-108">사용자의 로그인 이름 가져오기</span><span class="sxs-lookup"><span data-stu-id="16c7d-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="16c7d-109">애플리케이션이 Windows 인증을 사용하는 경우 사용자의 도메인 이름 가져오기</span><span class="sxs-lookup"><span data-stu-id="16c7d-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="16c7d-110">사용자의 역할 확인</span><span class="sxs-lookup"><span data-stu-id="16c7d-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="16c7d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16c7d-111">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.User>
