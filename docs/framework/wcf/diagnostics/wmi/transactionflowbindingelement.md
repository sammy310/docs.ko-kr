---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234897"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="4fd8e-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="4fd8e-102">TransactionFlowBindingElement</span></span>

<span data-ttu-id="4fd8e-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="4fd8e-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fd8e-104">구문</span><span class="sxs-lookup"><span data-stu-id="4fd8e-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4fd8e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4fd8e-105">Methods</span></span>  

 <span data-ttu-id="4fd8e-106">TransactionFlowBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd8e-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4fd8e-107">속성</span><span class="sxs-lookup"><span data-stu-id="4fd8e-107">Properties</span></span>  

 <span data-ttu-id="4fd8e-108">TransactionFlowBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd8e-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="4fd8e-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="4fd8e-109">IssuedTokens</span></span>  

 <span data-ttu-id="4fd8e-110">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="4fd8e-110">Data type: string</span></span>  
  
 <span data-ttu-id="4fd8e-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4fd8e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fd8e-112">발급된 보안 토큰 헤더(WS-Trust의 IssuedTokens)의 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd8e-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="4fd8e-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="4fd8e-113">TransactionProtocol</span></span>  

 <span data-ttu-id="4fd8e-114">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="4fd8e-114">Data type: string</span></span>  
  
 <span data-ttu-id="4fd8e-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4fd8e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fd8e-116">서비스에서 트랜잭션을 이동하는 데 사용하는 트랜잭션 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="4fd8e-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="4fd8e-117">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4fd8e-117">Transactions</span></span>  

 <span data-ttu-id="4fd8e-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4fd8e-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fd8e-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4fd8e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fd8e-120">들어오는 트랜잭션이 지원되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4fd8e-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fd8e-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4fd8e-121">Requirements</span></span>  
  
|<span data-ttu-id="4fd8e-122">MOF</span><span class="sxs-lookup"><span data-stu-id="4fd8e-122">MOF</span></span>|<span data-ttu-id="4fd8e-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd8e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4fd8e-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4fd8e-124">Namespace</span></span>|<span data-ttu-id="4fd8e-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd8e-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4fd8e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fd8e-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
