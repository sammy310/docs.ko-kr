---
description: '다음에 대 한 자세한 정보: 끝점: 보안 유효성 검사 및 인증 실패 수/초'
title: '엔드포인트: Security Validation and Authentication Failures Per Second'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: aa5ccc4049dc81a7c2d545cfc70e9078ac72d87a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655437"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="d2fc5-103">엔드포인트: Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="d2fc5-103">Endpoint: Security Validation and Authentication Failures Per Second</span></span>

<span data-ttu-id="d2fc5-104">카운터 이름: Security Validation and Authentication Failures Per Second</span><span class="sxs-lookup"><span data-stu-id="d2fc5-104">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="d2fc5-105">설명</span><span class="sxs-lookup"><span data-stu-id="d2fc5-105">Description</span></span>  

 <span data-ttu-id="d2fc5-106">이 카운터는 "Security Calls Not Authorized" 카운터로 처리되지 않는 보안 문제 때문에 메시지가 거부될 때마다 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fc5-106">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="d2fc5-107">이러한 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fc5-107">Such problems include:</span></span>  
  
- <span data-ttu-id="d2fc5-108">클라이언트 토큰을 메시지에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fc5-108">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="d2fc5-109">클라이언트 토큰에서 인증에 실패했습니다(예: 잘못된 암호).</span><span class="sxs-lookup"><span data-stu-id="d2fc5-109">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="d2fc5-110">서명 확인에 실패했습니다(예: 메시지 변조).</span><span class="sxs-lookup"><span data-stu-id="d2fc5-110">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="d2fc5-111">메시지가 이전 메시지와 중복됩니다. 이러한 현상은 재생 공격 중에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fc5-111">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="d2fc5-112">해독 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fc5-112">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="d2fc5-113">일부 필수 요소(예: 타임스탬프 또는 암호화된 데이터 블록)가 메시지에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fc5-113">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="d2fc5-114">TLSNEGO/SPNEGO 핸드셰이크 중에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fc5-114">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="d2fc5-115">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="d2fc5-115">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="d2fc5-116">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="d2fc5-116">(N1-N0)/((D1-D0)/F)</span></span>
