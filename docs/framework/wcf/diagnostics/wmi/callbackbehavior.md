---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 9d8f4335c304d164daafeb0ad4de5b4e3bba4590
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973969"
---
# <a name="callbackbehavior"></a><span data-ttu-id="a5e75-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="a5e75-102">CallbackBehavior</span></span>
<span data-ttu-id="a5e75-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="a5e75-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5e75-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5e75-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a5e75-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a5e75-105">Methods</span></span>  
 <span data-ttu-id="a5e75-106">CallbackBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a5e75-107">속성</span><span class="sxs-lookup"><span data-stu-id="a5e75-107">Properties</span></span>  
 <span data-ttu-id="a5e75-108">CallbackBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="a5e75-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="a5e75-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="a5e75-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="a5e75-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="a5e75-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a5e75-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5e75-112">true이면 서비스가 이중 세션을 닫을 경우 세션이 자동으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="a5e75-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="a5e75-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="a5e75-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="a5e75-114">Data type: string</span></span>  
<span data-ttu-id="a5e75-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a5e75-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5e75-116">서비스가 하나의 스레드, 여러 개의 스레드 또는 재진입 호출을 지원할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="a5e75-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="a5e75-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="a5e75-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="a5e75-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="a5e75-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a5e75-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5e75-120">연결되어 있는 알 수 없는 serialization 데이터를 보낼지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="a5e75-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="a5e75-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="a5e75-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="a5e75-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="a5e75-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a5e75-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5e75-124">선택하면 콜백 시 예외에 대한 세부 정보가 서비스로 반환되는 오류에 첨부됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="a5e75-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="a5e75-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="a5e75-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="a5e75-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="a5e75-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a5e75-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5e75-128">serialize된 개체에 허용되는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="a5e75-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="a5e75-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="a5e75-130">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="a5e75-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="a5e75-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a5e75-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5e75-132">현재 동기화 컨텍스트를 사용하여 스레드 실행을 선택할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="a5e75-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="a5e75-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="a5e75-134">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="a5e75-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="a5e75-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a5e75-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5e75-136">시스템 또는 응용 프로그램에서 SOAP MustUnderstand 헤더 처리를 적용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5e75-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5e75-137">Requirements</span></span>  
  
|<span data-ttu-id="a5e75-138">MOF</span><span class="sxs-lookup"><span data-stu-id="a5e75-138">MOF</span></span>|<span data-ttu-id="a5e75-139">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a5e75-140">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a5e75-140">Namespace</span></span>|<span data-ttu-id="a5e75-141">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e75-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5e75-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5e75-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
