---
ms.openlocfilehash: 15418d1ac3ade6a0fa35ca61a02134e20af1baea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602743"
---

<span data-ttu-id="2bcd6-101">.NET Core 패키지를 설치할 때 `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`와 유사한 오류가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcd6-101">While installing the .NET Core package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="2bcd6-102">이 오류는 .NET Core의 패키지 피드가 최신 패키지 버전으로 업그레이드되고 있으며 나중에 다시 시도해야 함을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcd6-102">This error could mean that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="2bcd6-103">업그레이드하는 동안 30분 이상 패키지 피드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcd6-103">During an upgrade, the package feed shouldn't be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="2bcd6-104">이 오류 메시지가 30분 이상 계속 표시되는 경우 <https://github.com/dotnet/core/issues>에서 문제를 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="2bcd6-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
