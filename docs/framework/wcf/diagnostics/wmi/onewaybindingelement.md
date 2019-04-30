---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 016ff823eb2c84a9f54c0763edadef1224e31517
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040053"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="bbee8-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="bbee8-102">OneWayBindingElement</span></span>
<span data-ttu-id="bbee8-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="bbee8-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbee8-104">구문</span><span class="sxs-lookup"><span data-stu-id="bbee8-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bbee8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bbee8-105">Methods</span></span>  
 <span data-ttu-id="bbee8-106">OneWayBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbee8-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bbee8-107">속성</span><span class="sxs-lookup"><span data-stu-id="bbee8-107">Properties</span></span>  
 <span data-ttu-id="bbee8-108">OneWayBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbee8-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="bbee8-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="bbee8-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="bbee8-110">데이터 형식: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="bbee8-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="bbee8-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bbee8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bbee8-112">채널 풀 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="bbee8-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="bbee8-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="bbee8-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="bbee8-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="bbee8-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="bbee8-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bbee8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bbee8-116">허용되는 최대 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bbee8-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="bbee8-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="bbee8-117">PacketRoutable</span></span>  
 <span data-ttu-id="bbee8-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="bbee8-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="bbee8-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bbee8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bbee8-120">패킷을 라우팅할 수 있는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbee8-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbee8-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbee8-121">Requirements</span></span>  
  
|<span data-ttu-id="bbee8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="bbee8-122">MOF</span></span>|<span data-ttu-id="bbee8-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbee8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bbee8-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="bbee8-124">Namespace</span></span>|<span data-ttu-id="bbee8-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbee8-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbee8-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="bbee8-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
