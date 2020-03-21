---
title: GetDemultiplexedStub 함수(관리되지 않는 API 참조)
description: GetDemultiplexedStub 함수는 클라이언트가 Windows 관리에서 비동기 호출을 수신하는 데 도움이 되도록 개체 전달자 싱크를 만듭니다.
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
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174968"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="59541-103">GetDemultiplexedStub 함수</span><span class="sxs-lookup"><span data-stu-id="59541-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="59541-104">클라이언트가 Windows 관리에서 비동기 호출을 수신하는 데 도움이 되는 개체 전달자 싱크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59541-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="59541-105">구문</span><span class="sxs-lookup"><span data-stu-id="59541-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="59541-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59541-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="59541-107">【인】 [IWbemObjectSink의](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)클라이언트 의 프로세스 내 구현에 대한 포인터 .</span><span class="sxs-lookup"><span data-stu-id="59541-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="59541-108">【인】 이벤트가 로컬인지 여부를 나타내는 플래그`true`(); 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="59541-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="59541-109">【아웃】 클라이언트가 Windows 관리에서 비동기 호출을 수신하는 데 도움이 되는 개체 전달자 싱크입니다.</span><span class="sxs-lookup"><span data-stu-id="59541-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="59541-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="59541-110">Return value</span></span>

<span data-ttu-id="59541-111">함수가 성공하면 반환 값은 `S_OK` (0)입니다.</span><span class="sxs-lookup"><span data-stu-id="59541-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="59541-112">함수가 실패하면 반환 값은 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="59541-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="59541-113">확장 오류 정보를 얻으려면 [GetErrorInfo](geterrorinfo.md) 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="59541-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="59541-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59541-114">Requirements</span></span>  
 <span data-ttu-id="59541-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59541-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59541-116">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="59541-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="59541-117">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59541-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59541-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59541-118">See also</span></span>

- [<span data-ttu-id="59541-119">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="59541-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
