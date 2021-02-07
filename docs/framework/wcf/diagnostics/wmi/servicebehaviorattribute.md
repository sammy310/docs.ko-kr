---
description: '자세히 알아보기: ServiceBehaviorAttribute'
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: 57ffa9103523618db752b3be6d43bb16603d1728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715576"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="25f97-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="25f97-103">ServiceBehaviorAttribute</span></span>

<span data-ttu-id="25f97-104">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="25f97-104">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f97-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="25f97-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="25f97-106">메서드</span><span class="sxs-lookup"><span data-stu-id="25f97-106">Methods</span></span>  

 <span data-ttu-id="25f97-107">ServiceBehaviorAttribute 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-107">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="25f97-108">속성</span><span class="sxs-lookup"><span data-stu-id="25f97-108">Properties</span></span>  

 <span data-ttu-id="25f97-109">ServiceBehaviorAttribute 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-109">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="25f97-110">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="25f97-110">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="25f97-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="25f97-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="25f97-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-113">클라이언트가 출력 세션을 닫을 때 세션을 자동으로 닫을지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-113">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="25f97-114">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="25f97-114">ConcurrencyMode</span></span>  

 <span data-ttu-id="25f97-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="25f97-115">Data type: string</span></span>  
<span data-ttu-id="25f97-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-117">서비스가 하나의 스레드, 여러 개의 스레드 또는 재진입 호출을 지원할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-117">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="25f97-118">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="25f97-118">ConfigurationName</span></span>  

 <span data-ttu-id="25f97-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="25f97-119">Data type: string</span></span>  
  
 <span data-ttu-id="25f97-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-121">서비스 구성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-121">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="25f97-122">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="25f97-122">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="25f97-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="25f97-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="25f97-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-125">네트워크에서 알 수 없는 serialization 데이터를 보낼지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-125">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="25f97-126">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="25f97-126">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="25f97-127">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="25f97-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="25f97-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-129">디버깅 목적으로 클라이언트에 반환되는 SOAP 오류 정보에 관리되는 예외 정보를 포함할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-129">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="25f97-130">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="25f97-130">InstanceContextMode</span></span>  

 <span data-ttu-id="25f97-131">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="25f97-131">Data type: string</span></span>  
  
 <span data-ttu-id="25f97-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-133">새 서비스 개체를 만드는 시점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-133">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="25f97-134">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="25f97-134">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="25f97-135">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="25f97-135">Data type: sint32</span></span>  
  
 <span data-ttu-id="25f97-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-137">serialize된 개체에 허용되는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-137">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="25f97-138">Name</span><span class="sxs-lookup"><span data-stu-id="25f97-138">Name</span></span>  

 <span data-ttu-id="25f97-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="25f97-139">Data type: string</span></span>  
  
 <span data-ttu-id="25f97-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-141">WSDL 서비스의 이름 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-141">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="25f97-142">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="25f97-142">Namespace</span></span>  

 <span data-ttu-id="25f97-143">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="25f97-143">Data type: string</span></span>  
  
 <span data-ttu-id="25f97-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-145">WSDL 서비스의 대상 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-145">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="25f97-146">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="25f97-146">ReleaseServiceInstanceOnTransactionComplete</span></span>  

 <span data-ttu-id="25f97-147">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="25f97-147">Data type: boolean</span></span>  
  
 <span data-ttu-id="25f97-148">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-149">현재 트랜잭션이 완료되면 서비스 개체를 재활용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-149">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="25f97-150">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="25f97-150">TransactionAutoCompleteOnSessionClose</span></span>  

 <span data-ttu-id="25f97-151">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="25f97-151">Data type: boolean</span></span>  
  
 <span data-ttu-id="25f97-152">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-153">현재 세션이 닫히면 보류 중인 트랜잭션을 완료할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-153">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="25f97-154">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="25f97-154">TransactionIsolationLevel</span></span>  

 <span data-ttu-id="25f97-155">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="25f97-155">Data type: string</span></span>  
  
 <span data-ttu-id="25f97-156">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-157">트랜잭션 격리 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-157">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="25f97-158">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="25f97-158">TransactionTimeout</span></span>  

 <span data-ttu-id="25f97-159">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="25f97-159">Data type: datetime</span></span>  
  
 <span data-ttu-id="25f97-160">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-160">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-161">트랜잭션을 완료해야 하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-161">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="25f97-162">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="25f97-162">UseSynchronizationContext</span></span>  

 <span data-ttu-id="25f97-163">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="25f97-163">Data type: boolean</span></span>  
  
 <span data-ttu-id="25f97-164">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-164">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-165">현재 동기화 컨텍스트를 사용하여 스레드 실행을 선택할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-165">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="25f97-166">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="25f97-166">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="25f97-167">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="25f97-167">Data type: boolean</span></span>  
  
 <span data-ttu-id="25f97-168">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="25f97-168">Access type: Read-only</span></span>  
  
 <span data-ttu-id="25f97-169">시스템 또는 애플리케이션에서 SOAP MustUnderstand 헤더 처리를 적용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-169">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f97-170">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25f97-170">Requirements</span></span>  
  
|<span data-ttu-id="25f97-171">MOF</span><span class="sxs-lookup"><span data-stu-id="25f97-171">MOF</span></span>|<span data-ttu-id="25f97-172">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-172">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="25f97-173">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="25f97-173">Namespace</span></span>|<span data-ttu-id="25f97-174">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25f97-174">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25f97-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25f97-175">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
