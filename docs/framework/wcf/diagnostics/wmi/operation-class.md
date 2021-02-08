---
description: '자세한 정보: Operation 클래스'
title: 작업 클래스
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 035c02bc05b7a64c5d15538001dbdcf2ec0b135b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803076"
---
# <a name="operation-class"></a><span data-ttu-id="14336-103">작업 클래스</span><span class="sxs-lookup"><span data-stu-id="14336-103">Operation class</span></span>

<span data-ttu-id="14336-104">작업</span><span class="sxs-lookup"><span data-stu-id="14336-104">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14336-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="14336-105">Syntax</span></span>  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="14336-106">메서드</span><span class="sxs-lookup"><span data-stu-id="14336-106">Methods</span></span>  

 <span data-ttu-id="14336-107">Operation 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14336-107">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="14336-108">속성</span><span class="sxs-lookup"><span data-stu-id="14336-108">Properties</span></span>  

 <span data-ttu-id="14336-109">Operation 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14336-109">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="14336-110">작업</span><span class="sxs-lookup"><span data-stu-id="14336-110">Action</span></span>  

 <span data-ttu-id="14336-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="14336-111">Data type: string</span></span>  
  
 <span data-ttu-id="14336-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-113">요청 메시지의 WS-Addressing 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="14336-113">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="14336-114">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="14336-114">AsyncPattern</span></span>  

 <span data-ttu-id="14336-115">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="14336-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="14336-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-117">`Begin`서비스 계약에서 [열기/닫기 꺾쇠 괄호]와 `End` [open/close 꺾쇠 괄호] 메서드 쌍을 사용 하 여 작업이 비동기적으로 구현 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="14336-117">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="14336-118">동작</span><span class="sxs-lookup"><span data-stu-id="14336-118">Behaviors</span></span>  

 <span data-ttu-id="14336-119">데이터 형식: Behavior array</span><span class="sxs-lookup"><span data-stu-id="14336-119">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="14336-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-121">이 작업과 연관된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="14336-121">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="14336-122">IsCallback</span><span class="sxs-lookup"><span data-stu-id="14336-122">IsCallback</span></span>  

 <span data-ttu-id="14336-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="14336-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="14336-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-125">작업이 콜백 작업인 경우 true입니다.</span><span class="sxs-lookup"><span data-stu-id="14336-125">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="14336-126">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="14336-126">IsInitiating</span></span>  

 <span data-ttu-id="14336-127">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="14336-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="14336-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-129">서버에서 세션을 시작할 수 있는 작업을 메서드에서 구현하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="14336-129">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="14336-130">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="14336-130">IsOneWay</span></span>  

 <span data-ttu-id="14336-131">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="14336-131">Data type: boolean</span></span>  
  
 <span data-ttu-id="14336-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-133">작업에서 회신 메시지를 반환하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="14336-133">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="14336-134">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="14336-134">IsTerminating</span></span>  

 <span data-ttu-id="14336-135">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="14336-135">Data type: boolean</span></span>  
  
 <span data-ttu-id="14336-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-137">작업에서 회신 메시지를 반환하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="14336-137">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="14336-138">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="14336-138">MethodSignature</span></span>  

 <span data-ttu-id="14336-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="14336-139">Data type: string</span></span>  
  
 <span data-ttu-id="14336-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-141">작업의 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="14336-141">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="14336-142">Name</span><span class="sxs-lookup"><span data-stu-id="14336-142">Name</span></span>  

 <span data-ttu-id="14336-143">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="14336-143">Data type: string</span></span>  
  
 <span data-ttu-id="14336-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-145">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="14336-145">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="14336-146">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="14336-146">ParameterTypes</span></span>  

 <span data-ttu-id="14336-147">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="14336-147">Data type: string array</span></span>  
  
 <span data-ttu-id="14336-148">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-149">작업의 매개 변수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="14336-149">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="14336-150">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="14336-150">ReplyAction</span></span>  

 <span data-ttu-id="14336-151">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="14336-151">Data type: string</span></span>  
  
 <span data-ttu-id="14336-152">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-153">작업의 회신 메시지에 대한 SOAP 동작 값입니다.</span><span class="sxs-lookup"><span data-stu-id="14336-153">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="14336-154">ReturnType</span><span class="sxs-lookup"><span data-stu-id="14336-154">ReturnType</span></span>  

 <span data-ttu-id="14336-155">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="14336-155">Data type: string</span></span>  
  
 <span data-ttu-id="14336-156">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="14336-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="14336-157">작업의 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="14336-157">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14336-158">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14336-158">Requirements</span></span>  
  
|<span data-ttu-id="14336-159">MOF</span><span class="sxs-lookup"><span data-stu-id="14336-159">MOF</span></span>|<span data-ttu-id="14336-160">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14336-160">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="14336-161">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="14336-161">Namespace</span></span>|<span data-ttu-id="14336-162">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14336-162">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14336-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14336-163">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
