---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: b6221e93f10b87a368bd594932a8c36ae14df8f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772832"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="603c7-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="603c7-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="603c7-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="603c7-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="603c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="603c7-104">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="603c7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="603c7-105">Methods</span></span>  
 <span data-ttu-id="603c7-106">ServiceBehaviorAttribute 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="603c7-107">속성</span><span class="sxs-lookup"><span data-stu-id="603c7-107">Properties</span></span>  
 <span data-ttu-id="603c7-108">ServiceBehaviorAttribute 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="603c7-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="603c7-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="603c7-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="603c7-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="603c7-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-112">클라이언트가 출력 세션을 닫을 때 세션을 자동으로 닫을지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="603c7-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="603c7-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="603c7-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="603c7-114">Data type: string</span></span>  
<span data-ttu-id="603c7-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-116">서비스가 하나의 스레드, 여러 개의 스레드 또는 재진입 호출을 지원할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="603c7-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="603c7-117">ConfigurationName</span></span>  
 <span data-ttu-id="603c7-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="603c7-118">Data type: string</span></span>  
  
 <span data-ttu-id="603c7-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-120">서비스 구성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="603c7-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="603c7-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="603c7-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="603c7-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="603c7-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-124">네트워크에서 알 수 없는 serialization 데이터를 보낼지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="603c7-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="603c7-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="603c7-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="603c7-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="603c7-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-128">디버깅 목적으로 클라이언트에 반환되는 SOAP 오류 정보에 관리되는 예외 정보를 포함할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="603c7-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="603c7-129">InstanceContextMode</span></span>  
 <span data-ttu-id="603c7-130">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="603c7-130">Data type: string</span></span>  
  
 <span data-ttu-id="603c7-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-132">새 서비스 개체를 만드는 시점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="603c7-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="603c7-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="603c7-134">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="603c7-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="603c7-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-136">serialize된 개체에 허용되는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="603c7-137">이름</span><span class="sxs-lookup"><span data-stu-id="603c7-137">Name</span></span>  
 <span data-ttu-id="603c7-138">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="603c7-138">Data type: string</span></span>  
  
 <span data-ttu-id="603c7-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-140">WSDL 서비스의 이름 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="603c7-141">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="603c7-141">Namespace</span></span>  
 <span data-ttu-id="603c7-142">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="603c7-142">Data type: string</span></span>  
  
 <span data-ttu-id="603c7-143">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-144">WSDL 서비스의 대상 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="603c7-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="603c7-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="603c7-146">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="603c7-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="603c7-147">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-148">현재 트랜잭션이 완료되면 서비스 개체를 재활용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="603c7-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="603c7-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="603c7-150">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="603c7-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="603c7-151">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-152">현재 세션이 닫히면 보류 중인 트랜잭션을 완료할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="603c7-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="603c7-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="603c7-154">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="603c7-154">Data type: string</span></span>  
  
 <span data-ttu-id="603c7-155">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-156">트랜잭션 격리 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="603c7-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="603c7-157">TransactionTimeout</span></span>  
 <span data-ttu-id="603c7-158">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="603c7-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="603c7-159">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-160">트랜잭션을 완료해야 하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="603c7-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="603c7-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="603c7-162">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="603c7-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="603c7-163">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-164">현재 동기화 컨텍스트를 사용하여 스레드 실행을 선택할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="603c7-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="603c7-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="603c7-166">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="603c7-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="603c7-167">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="603c7-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="603c7-168">시스템 또는 응용 프로그램에서 SOAP MustUnderstand 헤더 처리를 적용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="603c7-169">요구 사항</span><span class="sxs-lookup"><span data-stu-id="603c7-169">Requirements</span></span>  
  
|<span data-ttu-id="603c7-170">MOF</span><span class="sxs-lookup"><span data-stu-id="603c7-170">MOF</span></span>|<span data-ttu-id="603c7-171">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="603c7-172">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="603c7-172">Namespace</span></span>|<span data-ttu-id="603c7-173">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="603c7-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="603c7-174">참고자료</span><span class="sxs-lookup"><span data-stu-id="603c7-174">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
