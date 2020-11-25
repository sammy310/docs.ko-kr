---
title: GetDemultiplexedStub 함수 (관리 되지 않는 API 참조)
description: GetDemultiplexedStub 함수는 클라이언트에서 Windows 관리를 통해 비동기 호출을 받을 수 있도록 개체 전달자 싱크를 만듭니다.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f8f9b56268168bb16c476a9366facd17e8ac44e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730632"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="19580-103">GetDemultiplexedStub 함수</span><span class="sxs-lookup"><span data-stu-id="19580-103">GetDemultiplexedStub function</span></span>

<span data-ttu-id="19580-104">클라이언트가 Windows 관리에서 비동기 호출을 수신하는 데 도움이 되는 개체 전달자 싱크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="19580-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="19580-105">구문</span><span class="sxs-lookup"><span data-stu-id="19580-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="19580-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19580-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="19580-107">진행 [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)의 클라이언트 in-process 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="19580-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="19580-108">진행 이벤트가 로컬 () 인지 여부를 나타내는 플래그 `true` 이거나, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="19580-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="19580-109">제한이 클라이언트에서 Windows 관리를 통해 비동기 호출을 받을 수 있도록 지 원하는 개체 전달자 싱크입니다.</span><span class="sxs-lookup"><span data-stu-id="19580-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="19580-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="19580-110">Return value</span></span>

<span data-ttu-id="19580-111">함수가 성공 하면 반환 값은 `S_OK` (0)입니다.</span><span class="sxs-lookup"><span data-stu-id="19580-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="19580-112">함수가 실패 하면 반환 값은 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="19580-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="19580-113">확장 오류 정보를 가져오려면 [Geterrorinfo](geterrorinfo.md) 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="19580-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="19580-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19580-114">Requirements</span></span>  

 <span data-ttu-id="19580-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19580-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19580-116">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="19580-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="19580-117">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="19580-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19580-118">참조</span><span class="sxs-lookup"><span data-stu-id="19580-118">See also</span></span>

- [<span data-ttu-id="19580-119">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="19580-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
