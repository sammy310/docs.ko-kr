---
title: _CorDllMain 함수
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c509f475d5bf0105ece9791ee3e51d21c298a31f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666917"
---
# <a name="cordllmain-function"></a><span data-ttu-id="9b262-102">\_CorDllMain 함수</span><span class="sxs-lookup"><span data-stu-id="9b262-102">\_CorDllMain Function</span></span>

<span data-ttu-id="9b262-103">CLR (공용 언어 런타임)을 초기화 하 고 DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾습니다 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b262-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b262-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b262-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b262-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="9b262-106">[in] 로드 된 모듈의 인스턴스 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="9b262-107">[in] DLL 진입점 함수가 호출 되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="9b262-108">이 매개 변수는 다음 값 중 하나일 수 있습니다. DLL\_PROCESS_ATTACH, DLL\_스레드\_연결, DLL\_스레드\_ATTACH 또는 DLL\_프로세스\_분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="9b262-109">이러한 값의 설명을 보려면는 `DllMain` Platform SDK에 대 한 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="9b262-110">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b262-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="9b262-111">Return Value</span></span>  
 <span data-ttu-id="9b262-112">이 메서드는 반환 `true` 성공을 위한 및 `false` 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b262-113">설명</span><span class="sxs-lookup"><span data-stu-id="9b262-113">Remarks</span></span>  
 <span data-ttu-id="9b262-114">이 함수는 DLL 어셈블리에 대 한 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="9b262-115">실행 가능 어셈블리 로더 호출을 [ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 함수를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="9b262-116">운영 체제 로더는 DLL 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="9b262-117">`_CorDllMain` 함수는 운영 체제 로더에 의해 직접 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="9b262-118">자세한 내용은 주의 섹션을 참조 합니다 [ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="9b262-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b262-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b262-119">Requirements</span></span>  

 <span data-ttu-id="9b262-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b262-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b262-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b262-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b262-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9b262-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b262-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b262-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b262-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b262-124">See also</span></span>

- [<span data-ttu-id="9b262-125">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="9b262-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
