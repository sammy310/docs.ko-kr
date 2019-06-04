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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07d2f08792b6fdea28bd56045de8da30ab552a4f
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490578"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="da82b-102">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="da82b-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="da82b-103">XML 파일에서 읽은 버전 정보를 사용 하 여 프로세스에는 CLR (공용 언어 런타임)을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="da82b-104">.NET Framework 4에서이 함수에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da82b-105">구문</span><span class="sxs-lookup"><span data-stu-id="da82b-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da82b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da82b-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="da82b-107">[in] 에 대 한 포인터는 `IStream` XML 파일을 읽는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="da82b-108">[in] 사용 하도록 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-108">[in] Reserved for future use.</span></span> <span data-ttu-id="da82b-109">값으로 0 (영)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="da82b-110">[in] 값을 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) CLR의 시작 동작을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="da82b-111">[in] 합니다 `CLSID` 중 하나를 구현 하는 coclass의 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="da82b-112">지원 되는 값은 CLSID_CorRuntimeHost CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="da82b-113">[in] 합니다 `IID` 중 합니다 `ICorRuntimeHost` 또는 `ICLRRuntimeHost` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="da82b-114">지원 되는 값은 IID_ICorRuntimeHost IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="da82b-115">[out] 반환 되는 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da82b-116">설명</span><span class="sxs-lookup"><span data-stu-id="da82b-116">Remarks</span></span>  
 <span data-ttu-id="da82b-117">XML 파일의 형식은 표준 응용 프로그램 구성 파일을 따라 모델링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="da82b-118">XML 파일에 대 한 자세한 내용은 참조 하세요. [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="da82b-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da82b-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da82b-119">Requirements</span></span>  
 <span data-ttu-id="da82b-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="da82b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da82b-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da82b-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da82b-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da82b-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da82b-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da82b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da82b-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="da82b-124">See also</span></span>

- [<span data-ttu-id="da82b-125">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="da82b-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="da82b-126">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="da82b-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="da82b-127">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="da82b-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="da82b-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="da82b-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="da82b-129">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da82b-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="da82b-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="da82b-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
