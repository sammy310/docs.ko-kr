---
description: '자세한 정보: CallbackBehavior'
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: fa9e403324afe818e247d1f751cce0ce7d5a6fb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757763"
---
# <a name="callbackbehavior"></a><span data-ttu-id="c54f8-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="c54f8-103">CallbackBehavior</span></span>

<span data-ttu-id="c54f8-104">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="c54f8-104">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c54f8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c54f8-105">Syntax</span></span>  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c54f8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c54f8-106">Methods</span></span>  

 <span data-ttu-id="c54f8-107">CallbackBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-107">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c54f8-108">속성</span><span class="sxs-lookup"><span data-stu-id="c54f8-108">Properties</span></span>  

 <span data-ttu-id="c54f8-109">CallbackBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-109">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="c54f8-110">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="c54f8-110">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="c54f8-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="c54f8-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="c54f8-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c54f8-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c54f8-113">true이면 서비스가 이중 세션을 닫을 경우 세션이 자동으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-113">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="c54f8-114">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="c54f8-114">ConcurrencyMode</span></span>  

 <span data-ttu-id="c54f8-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="c54f8-115">Data type: string</span></span>  
<span data-ttu-id="c54f8-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c54f8-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c54f8-117">서비스가 하나의 스레드, 여러 개의 스레드 또는 재진입 호출을 지원할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-117">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="c54f8-118">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="c54f8-118">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="c54f8-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="c54f8-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="c54f8-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c54f8-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c54f8-121">연결되어 있는 알 수 없는 serialization 데이터를 보낼지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-121">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="c54f8-122">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="c54f8-122">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="c54f8-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="c54f8-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="c54f8-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c54f8-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c54f8-125">선택하면 콜백 시 예외에 대한 세부 정보가 서비스로 반환되는 오류에 첨부됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-125">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="c54f8-126">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="c54f8-126">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="c54f8-127">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="c54f8-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="c54f8-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c54f8-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c54f8-129">serialize된 개체에 허용되는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-129">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="c54f8-130">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="c54f8-130">UseSynchronizationContext</span></span>  

 <span data-ttu-id="c54f8-131">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="c54f8-131">Data type: boolean</span></span>  
  
 <span data-ttu-id="c54f8-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c54f8-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c54f8-133">현재 동기화 컨텍스트를 사용하여 스레드 실행을 선택할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-133">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="c54f8-134">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="c54f8-134">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="c54f8-135">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="c54f8-135">Data type: boolean</span></span>  
  
 <span data-ttu-id="c54f8-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c54f8-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c54f8-137">시스템 또는 애플리케이션에서 SOAP MustUnderstand 헤더 처리를 적용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-137">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c54f8-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c54f8-138">Requirements</span></span>  
  
|<span data-ttu-id="c54f8-139">MOF</span><span class="sxs-lookup"><span data-stu-id="c54f8-139">MOF</span></span>|<span data-ttu-id="c54f8-140">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-140">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c54f8-141">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c54f8-141">Namespace</span></span>|<span data-ttu-id="c54f8-142">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54f8-142">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c54f8-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c54f8-143">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
