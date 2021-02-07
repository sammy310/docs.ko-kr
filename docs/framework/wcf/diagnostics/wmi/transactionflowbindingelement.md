---
description: '자세히 알아보기: TransactionFlowBindingElement'
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 6a96a83c563affdaef01a12d64bc1c13ab2f719e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757139"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="36310-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="36310-103">TransactionFlowBindingElement</span></span>

<span data-ttu-id="36310-104">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="36310-104">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36310-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36310-105">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="36310-106">메서드</span><span class="sxs-lookup"><span data-stu-id="36310-106">Methods</span></span>  

 <span data-ttu-id="36310-107">TransactionFlowBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36310-107">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="36310-108">속성</span><span class="sxs-lookup"><span data-stu-id="36310-108">Properties</span></span>  

 <span data-ttu-id="36310-109">TransactionFlowBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36310-109">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="36310-110">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="36310-110">IssuedTokens</span></span>  

 <span data-ttu-id="36310-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="36310-111">Data type: string</span></span>  
  
 <span data-ttu-id="36310-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="36310-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36310-113">발급된 보안 토큰 헤더(WS-Trust의 IssuedTokens)의 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36310-113">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="36310-114">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="36310-114">TransactionProtocol</span></span>  

 <span data-ttu-id="36310-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="36310-115">Data type: string</span></span>  
  
 <span data-ttu-id="36310-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="36310-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36310-117">서비스에서 트랜잭션을 이동하는 데 사용하는 트랜잭션 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="36310-117">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="36310-118">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="36310-118">Transactions</span></span>  

 <span data-ttu-id="36310-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="36310-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="36310-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="36310-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36310-121">들어오는 트랜잭션이 지원되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36310-121">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36310-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36310-122">Requirements</span></span>  
  
|<span data-ttu-id="36310-123">MOF</span><span class="sxs-lookup"><span data-stu-id="36310-123">MOF</span></span>|<span data-ttu-id="36310-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36310-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="36310-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="36310-125">Namespace</span></span>|<span data-ttu-id="36310-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36310-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36310-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36310-127">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
