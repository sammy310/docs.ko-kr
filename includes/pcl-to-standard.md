---
ms.openlocfilehash: eb0a5c8ac733f0db4e8356dca80f898bc7a72cfb
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471966"
---
> [!IMPORTANT]
> <span data-ttu-id="33513-101">새 응용 프로그램 개발에서는 .NET 구현의 매우 구체적인 하위 집합만 대상으로 하기 때문에 이식 가능한 클래스 라이브러리를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="33513-101">We strongly discourage the use of portable class libraries in new application development, because they target only a very specific subset of .NET implementations.</span></span> <span data-ttu-id="33513-102">.NET Framework와 다른 .NET 구현 간에 코드를 공유 하는 재사용 가능한 라이브러리를 빌드하는 경우에는 .NET Standard 2.0 라이브러리를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="33513-102">If you're building a reusable library to share code between .NET Framework and other .NET implementations, the recommended replacement is a .NET Standard 2.0 library.</span></span> <span data-ttu-id="33513-103">그렇지 않으면 .NET 5 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="33513-103">Otherwise, use .NET 5 or later.</span></span> <span data-ttu-id="33513-104">자세한 내용은 [.NET 표준](~/docs/standard/net-standard.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33513-104">For more information, see [.NET Standard](~/docs/standard/net-standard.md).</span></span>
