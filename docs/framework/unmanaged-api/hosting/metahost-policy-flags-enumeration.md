---
title: METAHOST_POLICY_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31ff93b6935c2237a5935c4b40cc30b4129edcd0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765234"
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="b98da-102">METAHOST_POLICY_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="b98da-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="b98da-103">대부분의 런타임 호스트에 공통 되는 바인딩 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="b98da-104">이 열거형은에서 사용 된 [iclrmetahostpolicy:: Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b98da-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b98da-105">구문</span><span class="sxs-lookup"><span data-stu-id="b98da-105">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b98da-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b98da-106">Members</span></span>  
  
|<span data-ttu-id="b98da-107">멤버</span><span class="sxs-lookup"><span data-stu-id="b98da-107">Member</span></span>|<span data-ttu-id="b98da-108">설명</span><span class="sxs-lookup"><span data-stu-id="b98da-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="b98da-109">현재 프로세스에 로드 되는 모든 공용 언어 런타임 (CLR)를 고려 하지 않는 높은 호환성 정책을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="b98da-110">고려 합니다만 설치 된 Clr 및 구성 요소의 기본 자체 어셈블리 파일는 선언 된 빌드 대상 버전 또는 구성 파일에서 파생 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="b98da-111">정확히 일치 하는 없는 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft의 내용을 기반으로 하는 경우 업그레이드 정책 버전 바인딩 결과에 적용\\합니다. NETFramework\Policy\Upgrades 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="b98da-112">것과 동일한 효과가 [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="b98da-113">호출에 제공 된 이미지는 새 프로세스에서 실행 된 것 처럼 바인딩 결과가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="b98da-114">현재 `GetRequestedRuntime` 로드할 런타임 집합을 무시 하 고 설치 된 런타임 집합에 대해 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="b98da-115">이 플래그는 호스트를를 시작할 때 EXE를 바인딩할 런타임을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="b98da-116">경우에 오류 대화 상자가 표시 됩니다 `GetRequestedRuntime` 입력된 매개 변수를 사용 하 여 호환 되는 런타임을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="b98da-117">부터는 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)],이 오류 대화 상자를 사용자는 적절 한 기능을 사용 하도록 설정 하는지 여부를 묻는 Windows 기능 대화 상자의 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="b98da-118">`GetRequestedRuntime` 바인딩 프로세스에 대 한 추가 입력으로 프로세스 이미지 (및 모든 해당 구성 파일)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="b98da-119">기본적으로 `GetRequestedRuntime` 프로세스 이미지 경로 (일반적으로 프로세스를 시작 하는 데 사용 된 EXE)으로 대체 되지 않습니다 바인딩할 런타임에 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="b98da-120">`GetRequestedRuntime` 구성 파일에 정보가 없는 경우 해당 SKU에 설치 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="b98da-121">이 구성 파일을.NET Framework의 기본 설치 보다 작은 Sku에서 정상적으로 실패 하지 않은 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="b98da-122">기본적으로 `GetRequestedRuntime` 구성 파일에서 SKU 특성을 지정 하지 않으면 해당 SKU에 설치 되어 있는지 확인 하지 않습니다 `<supportedRuntime />` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="b98da-123">`GetRequestedRuntime` 구성 파일에 정보가 없는 경우 해당 SKU에 설치 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-123">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="b98da-124">이 구성 파일을.NET Framework의 기본 설치 보다 작은 Sku에서 정상적으로 실패 하지 않은 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="b98da-125">기본적으로 `GetRequestedRuntime` 구성 파일에서 SKU 특성을 지정 하지 않으면 해당 SKU에 설치 되어 있는지 확인 하지 않습니다 `<supportedRuntime />` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="b98da-126">`GetRequestedRuntime` SEM_FAILCRITICALERRORS를 무시 해야 (호출 하 여 설정 됩니다는 [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) 함수), 오류 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-126">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="b98da-127">기본적으로 SEM_FAILCRITICALERRORS를 오류 대화 상자를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="b98da-128">다른 프로세스에서 상속 된 된 및 자동 오류 시나리오에서 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98da-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b98da-129">설명</span><span class="sxs-lookup"><span data-stu-id="b98da-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b98da-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b98da-130">Requirements</span></span>  
 <span data-ttu-id="b98da-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b98da-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b98da-132">**헤더:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="b98da-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="b98da-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b98da-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b98da-134">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b98da-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98da-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="b98da-135">See also</span></span>

- [<span data-ttu-id="b98da-136">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="b98da-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="b98da-137">GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="b98da-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
