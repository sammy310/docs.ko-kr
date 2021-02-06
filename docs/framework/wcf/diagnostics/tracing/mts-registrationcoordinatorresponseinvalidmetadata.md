---
description: 자세한 내용은 RegistrationCoordinatorResponseInvalidMetadata를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata
ms.date: 03/30/2017
ms.assetid: a174bbf5-0ffe-4fda-969d-e7fbd1996123
ms.openlocfilehash: 2eeb5955f2d0bf3afd01ebfc7474cbccbcb70980
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635690"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorresponseinvalidmetadata"></a><span data-ttu-id="a45ab-103">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata</span><span class="sxs-lookup"><span data-stu-id="a45ab-103">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata</span></span>

<span data-ttu-id="a45ab-104">WS-Atomic Transaction 프로토콜 서비스에서 잘못되었거나 호환되지 않는 메타데이터가 있는 엔드포인트 참조를 포함한 RegisterResponse 메시지를 코디네이터로부터 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ab-104">The WS-Atomic Transaction protocol service received a RegisterResponse message from its coordinator that contains an endpoint reference with invalid or incompatible metadata.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a45ab-105">설명</span><span class="sxs-lookup"><span data-stu-id="a45ab-105">Description</span></span>  

 <span data-ttu-id="a45ab-106">로컬 트랜잭션 관리자에서 상위 트랜잭션 관리자에 등록하려고 하는 경우 상위에서 RegisterResponse 메시지에 잘못된 주소를 반환하면 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ab-106">Traced when the local Transaction Manager tries to register with its superior Transaction Manager and the superior returns an invalid address within the RegisterResponse message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45ab-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a45ab-107">See also</span></span>

- [<span data-ttu-id="a45ab-108">추적</span><span class="sxs-lookup"><span data-stu-id="a45ab-108">Tracing</span></span>](index.md)
- [<span data-ttu-id="a45ab-109">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a45ab-109">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a45ab-110">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="a45ab-110">Administration and Diagnostics</span></span>](../index.md)
