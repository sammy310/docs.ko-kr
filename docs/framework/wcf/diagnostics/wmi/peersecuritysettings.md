---
description: '자세한 정보: PeerSecuritySettings'
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: a8b5b8c88e71cb46110fa35186599c0f9c366d17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803011"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="bdc06-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="bdc06-103">PeerSecuritySettings</span></span>

<span data-ttu-id="bdc06-104">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="bdc06-104">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc06-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdc06-105">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bdc06-106">메서드</span><span class="sxs-lookup"><span data-stu-id="bdc06-106">Methods</span></span>  

 <span data-ttu-id="bdc06-107">PeerSecuritySettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc06-107">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bdc06-108">속성</span><span class="sxs-lookup"><span data-stu-id="bdc06-108">Properties</span></span>  

 <span data-ttu-id="bdc06-109">PeerSecuritySettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc06-109">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="bdc06-110">모드</span><span class="sxs-lookup"><span data-stu-id="bdc06-110">Mode</span></span>  

 <span data-ttu-id="bdc06-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="bdc06-111">Data type: string</span></span>  
  
 <span data-ttu-id="bdc06-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bdc06-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdc06-113">바인딩으로 구성된 엔드포인트가 메시지 수준 보안을 사용하는지 또는 전송 수준 보안을 사용하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="bdc06-113">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="bdc06-114">전송</span><span class="sxs-lookup"><span data-stu-id="bdc06-114">Transport</span></span>  

 <span data-ttu-id="bdc06-115">데이터 형식: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="bdc06-115">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="bdc06-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bdc06-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdc06-117">전송 보안 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="bdc06-117">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdc06-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bdc06-118">Requirements</span></span>  
  
|<span data-ttu-id="bdc06-119">MOF</span><span class="sxs-lookup"><span data-stu-id="bdc06-119">MOF</span></span>|<span data-ttu-id="bdc06-120">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc06-120">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bdc06-121">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="bdc06-121">Namespace</span></span>|<span data-ttu-id="bdc06-122">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc06-122">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdc06-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdc06-123">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
