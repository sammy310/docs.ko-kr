---
description: '자세한 정보: 바인딩'
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: 36887a9296bfafd0790105e7f4d513efc3009bf8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757789"
---
# <a name="binding"></a><span data-ttu-id="dd0b1-103">바인딩</span><span class="sxs-lookup"><span data-stu-id="dd0b1-103">Binding</span></span>

<span data-ttu-id="dd0b1-104">wmi 바인딩</span><span class="sxs-lookup"><span data-stu-id="dd0b1-104">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd0b1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd0b1-105">Syntax</span></span>  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dd0b1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="dd0b1-106">Methods</span></span>  

 <span data-ttu-id="dd0b1-107">Binding 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-107">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dd0b1-108">속성</span><span class="sxs-lookup"><span data-stu-id="dd0b1-108">Properties</span></span>  

 <span data-ttu-id="dd0b1-109">바인딩 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-109">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="dd0b1-110">BindingElements</span><span class="sxs-lookup"><span data-stu-id="dd0b1-110">BindingElements</span></span>  

 <span data-ttu-id="dd0b1-111">데이터 형식: BindingElement array</span><span class="sxs-lookup"><span data-stu-id="dd0b1-111">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="dd0b1-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="dd0b1-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd0b1-113">바인딩이 구현한 바인딩 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-113">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="dd0b1-114">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="dd0b1-114">CloseTimeout</span></span>  

 <span data-ttu-id="dd0b1-115">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="dd0b1-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="dd0b1-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="dd0b1-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd0b1-117">닫기 작업을 완료하기 위해 제공된 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-117">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="dd0b1-118">Name</span><span class="sxs-lookup"><span data-stu-id="dd0b1-118">Name</span></span>  

 <span data-ttu-id="dd0b1-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="dd0b1-119">Data type: string</span></span>  
  
 <span data-ttu-id="dd0b1-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="dd0b1-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd0b1-121">바인딩 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-121">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="dd0b1-122">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="dd0b1-122">Namespace</span></span>  

 <span data-ttu-id="dd0b1-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="dd0b1-123">Data type: string</span></span>  
  
 <span data-ttu-id="dd0b1-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="dd0b1-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd0b1-125">바인딩의 XML 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-125">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="dd0b1-126">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="dd0b1-126">OpenTimeout</span></span>  

 <span data-ttu-id="dd0b1-127">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="dd0b1-127">Data type: datetime</span></span>  
  
 <span data-ttu-id="dd0b1-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="dd0b1-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd0b1-129">열기 작업을 완료하기 위해 제공된 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-129">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="dd0b1-130">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="dd0b1-130">ReceiveTimeout</span></span>  

 <span data-ttu-id="dd0b1-131">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="dd0b1-131">Data type: datetime</span></span>  
  
 <span data-ttu-id="dd0b1-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="dd0b1-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd0b1-133">받기 작업을 완료하기 위해 제공된 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-133">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="dd0b1-134">구성표</span><span class="sxs-lookup"><span data-stu-id="dd0b1-134">Scheme</span></span>  

 <span data-ttu-id="dd0b1-135">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="dd0b1-135">Data type: string</span></span>  
  
 <span data-ttu-id="dd0b1-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="dd0b1-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd0b1-137">바인딩이 빌드한 채널 및 수신기 팩터리에서 사용하는 URI 전송 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-137">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="dd0b1-138">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="dd0b1-138">SendTimeout</span></span>  

 <span data-ttu-id="dd0b1-139">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="dd0b1-139">Data type: datetime</span></span>  
  
 <span data-ttu-id="dd0b1-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="dd0b1-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd0b1-141">보내기 작업을 완료하기 위해 제공된 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-141">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd0b1-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd0b1-142">Requirements</span></span>  
  
|<span data-ttu-id="dd0b1-143">MOF</span><span class="sxs-lookup"><span data-stu-id="dd0b1-143">MOF</span></span>|<span data-ttu-id="dd0b1-144">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-144">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dd0b1-145">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="dd0b1-145">Namespace</span></span>|<span data-ttu-id="dd0b1-146">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd0b1-146">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd0b1-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd0b1-147">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
