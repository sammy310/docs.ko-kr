---
title: CorBindToCurrentRuntime 함수
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
ms.openlocfilehash: 348ca9d157a668dcd180076475f1fe9861197174
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616672"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="2f2f0-102">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="2f2f0-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="2f2f0-103">XML 파일에 저장 된 버전 정보를 사용 하 여 CLR (공용 언어 런타임)을 프로세스로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="2f2f0-104">XML 파일의 형식은 표준 응용 프로그램 구성 파일 다음에 모델링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="2f2f0-105">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-105">For more information about configuration files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="2f2f0-106">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-106">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="2f2f0-107">[프로세스에 공용 언어 런타임 로드](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-107">See [Loading the Common Language Runtime into a Process](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2f0-108">구문</span><span class="sxs-lookup"><span data-stu-id="2f2f0-108">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f2f0-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f2f0-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="2f2f0-110">진행 로드할 CLR 버전을 지정 하는 응용 프로그램 구성 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="2f2f0-111">파일 이름이 정규화 되지 않은 경우 호출을 수행 하는 실행 파일과 동일한 디렉터리에 있는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="2f2f0-112">로드할 런타임 버전은 구성 파일의 [ \< requiredruntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) 요소에 있는 version 특성으로 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="2f2f0-113">버전을 지정 하지 않거나 `<requiredRuntime>` 요소를 찾을 수 없는 경우 컴퓨터에 설치 된 CLR의 최신 버전이 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="2f2f0-114">진행 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="2f2f0-115">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="2f2f0-116">진행 `IID`요청 하는 인터페이스의입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="2f2f0-117">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2f2f0-118">제한이 반환 된 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f2f0-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f2f0-119">Requirements</span></span>  
 <span data-ttu-id="2f2f0-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2f0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f2f0-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2f2f0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f2f0-122">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2f2f0-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f2f0-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f2f0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2f0-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f2f0-124">See also</span></span>

- [<span data-ttu-id="2f2f0-125">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="2f2f0-125">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="2f2f0-126">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="2f2f0-126">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="2f2f0-127">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="2f2f0-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="2f2f0-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="2f2f0-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="2f2f0-129">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f2f0-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="2f2f0-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="2f2f0-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
