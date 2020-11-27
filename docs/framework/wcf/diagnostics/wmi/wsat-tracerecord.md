---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262218"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="5ab23-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="5ab23-102">WSAT_TraceRecord</span></span>

<span data-ttu-id="5ab23-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="5ab23-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab23-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ab23-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5ab23-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5ab23-105">Methods</span></span>  

 <span data-ttu-id="5ab23-106">WSAT_TraceRecord 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab23-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5ab23-107">속성</span><span class="sxs-lookup"><span data-stu-id="5ab23-107">Properties</span></span>  

 <span data-ttu-id="5ab23-108">WSAT_TraceRecord 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab23-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="5ab23-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="5ab23-109">ActivityID</span></span>  

 <span data-ttu-id="5ab23-110">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="5ab23-110">Data type: object</span></span>  
<span data-ttu-id="5ab23-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5ab23-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ab23-112">추적 레코드의 동작 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab23-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="5ab23-113">EventID</span><span class="sxs-lookup"><span data-stu-id="5ab23-113">EventID</span></span>  

 <span data-ttu-id="5ab23-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="5ab23-114">Data type: sint32</span></span>  
<span data-ttu-id="5ab23-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5ab23-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ab23-116">추적 레코드의 이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab23-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="5ab23-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="5ab23-117">TraceRecord</span></span>  

 <span data-ttu-id="5ab23-118">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="5ab23-118">Data type: string</span></span>  
<span data-ttu-id="5ab23-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5ab23-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ab23-120">추적 레코드</span><span class="sxs-lookup"><span data-stu-id="5ab23-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab23-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ab23-121">Requirements</span></span>  
  
|<span data-ttu-id="5ab23-122">MOF</span><span class="sxs-lookup"><span data-stu-id="5ab23-122">MOF</span></span>|<span data-ttu-id="5ab23-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab23-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5ab23-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="5ab23-124">Namespace</span></span>|<span data-ttu-id="5ab23-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab23-125">Defined in root\ServiceModel</span></span>|
