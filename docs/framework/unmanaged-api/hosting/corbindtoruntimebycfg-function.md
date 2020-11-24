---
title: CorBindToRuntimeByCfg 함수
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: d319382b577844a804c3e4562676491a15de5f63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673789"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="1de4d-102">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="1de4d-102">CorBindToRuntimeByCfg Function</span></span>

<span data-ttu-id="1de4d-103">XML 파일에서 읽은 버전 정보를 사용 하 여 CLR (공용 언어 런타임)을 프로세스로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="1de4d-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de4d-105">구문</span><span class="sxs-lookup"><span data-stu-id="1de4d-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1de4d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1de4d-106">Parameters</span></span>  

 `pCfgStream`  
 <span data-ttu-id="1de4d-107">진행 XML 파일을 읽는 개체에 대 한 포인터 `IStream` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="1de4d-108">진행 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-108">[in] Reserved for future use.</span></span> <span data-ttu-id="1de4d-109">값으로 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="1de4d-110">진행 CLR의 시작 동작을 지정 하는 [STARTUP_FLAGS](startup-flags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="1de4d-111">진행 [ICorRuntimeHost](icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="1de4d-112">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="1de4d-113">진행 `IID` 또는 인터페이스의입니다 `ICorRuntimeHost` `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="1de4d-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="1de4d-114">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="1de4d-115">제한이 반환 된 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1de4d-116">설명</span><span class="sxs-lookup"><span data-stu-id="1de4d-116">Remarks</span></span>  

 <span data-ttu-id="1de4d-117">XML 파일의 형식은 표준 응용 프로그램 구성 파일 다음에 모델링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de4d-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="1de4d-118">XML 파일에 대 한 자세한 내용은 [구성 파일 스키마](../../configure-apps/file-schema/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1de4d-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de4d-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1de4d-119">Requirements</span></span>  

 <span data-ttu-id="1de4d-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1de4d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de4d-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1de4d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1de4d-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1de4d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1de4d-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de4d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de4d-124">참조</span><span class="sxs-lookup"><span data-stu-id="1de4d-124">See also</span></span>

- [<span data-ttu-id="1de4d-125">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="1de4d-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="1de4d-126">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="1de4d-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="1de4d-127">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="1de4d-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="1de4d-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="1de4d-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="1de4d-129">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1de4d-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="1de4d-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="1de4d-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
