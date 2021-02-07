---
description: '다음에 대 한 자세한 정보: WSAT_TraceRecord'
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 67202c5d2910783c40b934d2da6108e6b514a728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756879"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="36360-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="36360-103">WSAT_TraceRecord</span></span>

<span data-ttu-id="36360-104">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="36360-104">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36360-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36360-105">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="36360-106">메서드</span><span class="sxs-lookup"><span data-stu-id="36360-106">Methods</span></span>  

 <span data-ttu-id="36360-107">WSAT_TraceRecord 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36360-107">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="36360-108">속성</span><span class="sxs-lookup"><span data-stu-id="36360-108">Properties</span></span>  

 <span data-ttu-id="36360-109">WSAT_TraceRecord 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36360-109">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="36360-110">ActivityID</span><span class="sxs-lookup"><span data-stu-id="36360-110">ActivityID</span></span>  

 <span data-ttu-id="36360-111">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="36360-111">Data type: object</span></span>  
<span data-ttu-id="36360-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="36360-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36360-113">추적 레코드의 동작 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="36360-113">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="36360-114">EventID</span><span class="sxs-lookup"><span data-stu-id="36360-114">EventID</span></span>  

 <span data-ttu-id="36360-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="36360-115">Data type: sint32</span></span>  
<span data-ttu-id="36360-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="36360-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36360-117">추적 레코드의 이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="36360-117">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="36360-118">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="36360-118">TraceRecord</span></span>  

 <span data-ttu-id="36360-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="36360-119">Data type: string</span></span>  
<span data-ttu-id="36360-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="36360-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="36360-121">추적 레코드</span><span class="sxs-lookup"><span data-stu-id="36360-121">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36360-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36360-122">Requirements</span></span>  
  
|<span data-ttu-id="36360-123">MOF</span><span class="sxs-lookup"><span data-stu-id="36360-123">MOF</span></span>|<span data-ttu-id="36360-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36360-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="36360-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="36360-125">Namespace</span></span>|<span data-ttu-id="36360-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36360-126">Defined in root\ServiceModel</span></span>|
