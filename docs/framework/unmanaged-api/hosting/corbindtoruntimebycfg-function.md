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
ms.openlocfilehash: 4fbc6e7ea531f65a6b1cd0ec93f4847ab8e4fe83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178241"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="08ae1-102">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="08ae1-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="08ae1-103">XML 파일에서 읽은 버전 정보를 사용하여 공통 언어 런타임(CLR)을 프로세스에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="08ae1-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ae1-105">구문</span><span class="sxs-lookup"><span data-stu-id="08ae1-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="08ae1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08ae1-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="08ae1-107">【인】 XML 파일을 `IStream` 읽는 개체에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="08ae1-108">【인】 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-108">[in] Reserved for future use.</span></span> <span data-ttu-id="08ae1-109">0(0)을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="08ae1-110">【인】 CLR의 시작 동작을 지정하는 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="08ae1-111">진행 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="08ae1-112">지원되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="08ae1-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="08ae1-113">【인】 또는 인터페이스 `IID` 중 `ICLRRuntimeHost` 하나. `ICorRuntimeHost`</span><span class="sxs-lookup"><span data-stu-id="08ae1-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="08ae1-114">지원되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="08ae1-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="08ae1-115">【아웃】 반환된 인터페이스의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08ae1-116">설명</span><span class="sxs-lookup"><span data-stu-id="08ae1-116">Remarks</span></span>  
 <span data-ttu-id="08ae1-117">XML 파일의 형식은 표준 응용 프로그램 구성 파일을 모델로 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ae1-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="08ae1-118">XML 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="08ae1-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08ae1-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08ae1-119">Requirements</span></span>  
 <span data-ttu-id="08ae1-120">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08ae1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08ae1-121">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="08ae1-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08ae1-122">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="08ae1-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08ae1-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08ae1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ae1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08ae1-124">See also</span></span>

- [<span data-ttu-id="08ae1-125">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="08ae1-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="08ae1-126">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="08ae1-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="08ae1-127">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="08ae1-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="08ae1-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="08ae1-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="08ae1-129">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08ae1-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="08ae1-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="08ae1-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
