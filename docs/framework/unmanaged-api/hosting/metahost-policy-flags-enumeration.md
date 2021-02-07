---
description: '다음에 대 한 자세한 정보: 열거형 METAHOST_POLICY_FLAGS'
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
ms.openlocfilehash: 3a3ebe602c8f048b7f9fc907f5d4741722bd0ed3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679625"
---
# <a name="metahost_policy_flags-enumeration"></a><span data-ttu-id="3339d-103">METAHOST_POLICY_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="3339d-103">METAHOST_POLICY_FLAGS Enumeration</span></span>

<span data-ttu-id="3339d-104">대부분의 런타임 호스트에 공통 되는 바인딩 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-104">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="3339d-105">이 열거형은 [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) 메서드에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-105">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3339d-106">구문</span><span class="sxs-lookup"><span data-stu-id="3339d-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="3339d-107">구성원</span><span class="sxs-lookup"><span data-stu-id="3339d-107">Members</span></span>  
  
|<span data-ttu-id="3339d-108">멤버</span><span class="sxs-lookup"><span data-stu-id="3339d-108">Member</span></span>|<span data-ttu-id="3339d-109">설명</span><span class="sxs-lookup"><span data-stu-id="3339d-109">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="3339d-110">현재 프로세스에 로드 되는 CLR (공용 언어 런타임)을 고려 하지 않는 높은 호환성 정책을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-110">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="3339d-111">대신 어셈블리 파일 자체, 선언 된 기본 제공 버전 또는 구성 파일에서 파생 된 구성 요소의 설치 된 Clr 및 기본 설정만 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-111">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="3339d-112">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft의 내용을 기준으로 정확히 일치 하는 항목을 찾을 수 없는 경우 버전 바인드 결과에 업그레이드 정책을 적용 \\ 합니다. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="3339d-112">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="3339d-113">[RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md)와 동일한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-113">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="3339d-114">호출에 제공 된 이미지가 새 프로세스에서 시작 된 것 처럼 바인딩 결과가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-114">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="3339d-115">현재는 `GetRequestedRuntime` 설치 된 런타임 집합에 대해 로드 가능한 런타임 집합과 바인딩 집합을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-115">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="3339d-116">이 플래그를 사용 하면 호스트에서 실행 될 때 EXE가 바인딩될 런타임을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-116">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="3339d-117">에서 `GetRequestedRuntime` 입력 매개 변수와 호환 되는 런타임을 찾을 수 없는 경우 오류 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-117">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="3339d-118">.NET Framework 4.5부터이 오류 대화 상자는 사용자가 적절 한 기능을 사용 하도록 설정할지 여부를 묻는 Windows 기능 대화 상자의 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-118">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="3339d-119">`GetRequestedRuntime` 는 프로세스 이미지 (및 해당 구성 파일)를 바인딩 프로세스에 대 한 추가 입력으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-119">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="3339d-120">기본적으로는 `GetRequestedRuntime` 바인딩할 런타임을 결정할 때 프로세스 이미지 경로 (일반적으로 프로세스를 시작 하는 데 사용 된 EXE)로 대체 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-120">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="3339d-121">`GetRequestedRuntime` 구성 파일에 사용할 수 있는 정보가 없을 때 적절 한 SKU가 설치 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-121">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="3339d-122">이렇게 하면 구성 파일이 없는 응용 프로그램이 .NET Framework의 기본 설치 보다 더 작은 Sku에서 정상적으로 장애 조치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-122">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="3339d-123">기본적으로에서는 `GetRequestedRuntime` 구성 파일 요소에 sku 특성이 지정 되지 않은 경우 적절 한 SKU가 설치 되어 있는지 여부를 확인 하지 않습니다 `<supportedRuntime />` .</span><span class="sxs-lookup"><span data-stu-id="3339d-123">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="3339d-124">`GetRequestedRuntime`[SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) 함수를 호출 하 여 설정 된 SEM_FAILCRITICALERRORS를 무시 하 고 오류 대화 상자를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-124">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function), and show the error dialog box.</span></span> <span data-ttu-id="3339d-125">기본적으로 SEM_FAILCRITICALERRORS는 오류 대화 상자를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-125">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="3339d-126">다른 프로세스에서 상속 되었을 수 있으며, 시나리오에서 자동 오류가 바람직하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-126">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3339d-127">설명</span><span class="sxs-lookup"><span data-stu-id="3339d-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3339d-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3339d-128">Requirements</span></span>  

 <span data-ttu-id="3339d-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3339d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3339d-130">**헤더:** Metahost</span><span class="sxs-lookup"><span data-stu-id="3339d-130">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="3339d-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3339d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3339d-132">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3339d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3339d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3339d-133">See also</span></span>

- [<span data-ttu-id="3339d-134">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="3339d-134">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="3339d-135">GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="3339d-135">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
