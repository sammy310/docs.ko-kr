---
description: '자세히 알아보기: CorBindToRuntimeByCfg 함수'
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
ms.openlocfilehash: c1acf6a8f1d8637bc2d6cd180016ff51cf500107
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790076"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="8b087-103">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="8b087-103">CorBindToRuntimeByCfg Function</span></span>

<span data-ttu-id="8b087-104">XML 파일에서 읽은 버전 정보를 사용 하 여 CLR (공용 언어 런타임)을 프로세스로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-104">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="8b087-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b087-106">구문</span><span class="sxs-lookup"><span data-stu-id="8b087-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8b087-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b087-107">Parameters</span></span>  

 `pCfgStream`  
 <span data-ttu-id="8b087-108">진행 XML 파일을 읽는 개체에 대 한 포인터 `IStream` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-108">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="8b087-109">진행 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-109">[in] Reserved for future use.</span></span> <span data-ttu-id="8b087-110">값으로 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-110">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="8b087-111">진행 CLR의 시작 동작을 지정 하는 [STARTUP_FLAGS](startup-flags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-111">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="8b087-112">진행 [ICorRuntimeHost](icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-112">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="8b087-113">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-113">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="8b087-114">진행 `IID` 또는 인터페이스의입니다 `ICorRuntimeHost` `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="8b087-114">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="8b087-115">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-115">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="8b087-116">제한이 반환 된 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-116">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b087-117">설명</span><span class="sxs-lookup"><span data-stu-id="8b087-117">Remarks</span></span>  

 <span data-ttu-id="8b087-118">XML 파일의 형식은 표준 응용 프로그램 구성 파일 다음에 모델링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b087-118">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="8b087-119">XML 파일에 대 한 자세한 내용은 [구성 파일 스키마](../../configure-apps/file-schema/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b087-119">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b087-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b087-120">Requirements</span></span>  

 <span data-ttu-id="8b087-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b087-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b087-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8b087-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b087-123">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b087-123">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b087-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b087-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b087-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b087-125">See also</span></span>

- [<span data-ttu-id="8b087-126">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="8b087-126">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="8b087-127">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="8b087-127">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="8b087-128">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="8b087-128">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="8b087-129">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="8b087-129">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="8b087-130">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b087-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="8b087-131">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="8b087-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
