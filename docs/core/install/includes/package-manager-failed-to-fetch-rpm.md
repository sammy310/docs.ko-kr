---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920726"
---

<span data-ttu-id="e42c2-101">.NET Core 패키지를 설치할 때 `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`와 유사한 오류가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e42c2-101">While installing the .NET Core package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="e42c2-102">일반적으로 이 오류는 .NET Core의 패키지 피드가 최신 패키지 버전으로 업그레이드되고 있으며 나중에 다시 시도해야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e42c2-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="e42c2-103">업그레이드하는 동안 2시간 이상 패키지 피드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e42c2-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="e42c2-104">이 오류 메시지가 2시간 이상 계속 표시되는 경우 <https://github.com/dotnet/core/issues>에서 문제를 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="e42c2-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
