---
title: 보안
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 보안
ms.date: 06/30/2019
ms.openlocfilehash: 848255de70038798417a558543d0b1ea8cff1e37
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840996"
---
# <a name="security"></a><span data-ttu-id="0f790-103">보안</span><span class="sxs-lookup"><span data-stu-id="0f790-103">Security</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="0f790-104">하루에는 문제가 발생 하는 회사에 대 한 일부 스토리가 포함 되지 않으며 고객의 데이터가 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-104">Not a day goes by where the news doesn't contain some story about a company being hacked or somehow losing their customers' data.</span></span> <span data-ttu-id="0f790-105">국가는 보안을 사실은로 처리 하 여 생성 된 문제에 면역 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-105">Even countries aren't immune to the problems created by treating security as an afterthought.</span></span> <span data-ttu-id="0f790-106">연도는 회사에서 고객 데이터의 보안을 처리 하 고 실제로는 "좋은" 것으로 전체 네트워크를 처리 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-106">For years, companies have treated the security of customer data and, in fact, their entire networks as something of a "nice to have".</span></span> <span data-ttu-id="0f790-107">Windows server는 패치가 적용 되지 않은 상태로 유지 되 고 PHP 버전의 PHP를 실행 하 고 MongoDB 데이터베이스를 전 세계에 열어 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-107">Windows servers were left unpatched, ancient versions of PHP kept running and MongoDB databases left wide open to the world.</span></span>

<span data-ttu-id="0f790-108">그러나 응용 프로그램을 빌드 및 배포할 때 보안 마음가짐을 유지 하지 않을 경우에는 실제 결과가 발생 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-108">However, there are starting to be real-world consequences for not maintaining a security mindset when building and deploying applications.</span></span> <span data-ttu-id="0f790-109">대부분의 회사에서는 [NotPetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/)의 2017 발생 중에 서버 및 데스크톱이 패치 되지 않은 경우 발생할 수 있는 문제를 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-109">Many companies learned the hard way what can happen when servers and desktops aren't patched during the 2017 outbreak of [NotPetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/).</span></span> <span data-ttu-id="0f790-110">이러한 공격의 비용은 10억 개에 쉽게 도달 했을 것 이며,이에 대 한 몇 가지 추정은 100억 미국 달러의 공격에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-110">The cost of these attacks has easily reached into the billions, with some estimates putting the losses from this single attack at 10 billion US dollars.</span></span>

<span data-ttu-id="0f790-111">정부도 해킹 인시던트에 면역 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-111">Even governments aren't immune to hacking incidents.</span></span> <span data-ttu-id="0f790-112">Baltimore의 도시는 시민 들이 요금을 지불 하거나 도시 서비스를 사용할 수 없도록 하는 ransom을 [보유 하 고](https://www.vox.com/recode/2019/5/21/18634505/baltimore-ransom-robbinhood-mayor-jack-young-hackers) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-112">The city of Baltimore was held ransom by [criminals](https://www.vox.com/recode/2019/5/21/18634505/baltimore-ransom-robbinhood-mayor-jack-young-hackers) making it impossible for citizens to pay their bills or use city services.</span></span>

<span data-ttu-id="0f790-113">또한 개인 데이터에 대 한 특정 데이터 보호를 요구 하는 법규가 증가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-113">There has also been an increase in legislation that mandates certain data protections for personal data.</span></span> <span data-ttu-id="0f790-114">유럽에서 GDPR은 1 년 이상에 적용 되었으며, 최근 캘리포니아는 2020 년 1 월 1 일에 적용 되는 CCDA 라는 자체 버전을 전달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-114">In Europe, GDPR has been in effect for more than a year and, more recently, California passed their own version called CCDA, which comes into effect January 1, 2020.</span></span> <span data-ttu-id="0f790-115">GDPR 아래의 벌금는 회사를 업무 외에 punishing 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-115">The fines under GDPR can be so punishing as to put companies out of business.</span></span> <span data-ttu-id="0f790-116">Google은 이미 위반에 대해 5000만 유로를 사용 했지만 잠재적 벌금 비교 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-116">Google has already been fined 50 million Euros for violations, but that's just a drop in the bucket compared with the potential fines.</span></span>

<span data-ttu-id="0f790-117">즉, 보안은 심각한 비즈니스입니다.</span><span class="sxs-lookup"><span data-stu-id="0f790-117">In short, security is serious business.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0f790-118">[이전](identity-server.md)
>[다음](azure-security.md)</span><span class="sxs-lookup"><span data-stu-id="0f790-118">[Previous](identity-server.md)
[Next](azure-security.md)</span></span>
