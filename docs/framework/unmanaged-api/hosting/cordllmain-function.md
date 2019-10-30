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
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136975"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="377d4-102">\_CorDllMain 함수</span><span class="sxs-lookup"><span data-stu-id="377d4-102">\_CorDllMain Function</span></span>

<span data-ttu-id="377d4-103">CLR (공용 언어 런타임)을 초기화 하 고, DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="377d4-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="377d4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="377d4-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="377d4-106">진행 로드 된 모듈의 인스턴스 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="377d4-107">진행 DLL 진입점 함수가 호출 되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="377d4-108">이 매개 변수는 다음 값 중 하나일 수 있습니다. DLL\_PROCESS_ATTACH, DLL\_스레드\_연결, DLL\_스레드\_연결 또는 DLL\_분리\_프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="377d4-109">이러한 값에 대 한 설명은 Platform SDK의 `DllMain` 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="377d4-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="377d4-110">진행 사용 되지 않는.</span><span class="sxs-lookup"><span data-stu-id="377d4-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="377d4-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="377d4-111">Return Value</span></span>  
 <span data-ttu-id="377d4-112">이 메서드는 성공에 `true`를 반환 하 고 오류가 발생 하는 경우 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="377d4-113">주의</span><span class="sxs-lookup"><span data-stu-id="377d4-113">Remarks</span></span>  
 <span data-ttu-id="377d4-114">이 함수는 DLL 어셈블리에 대 한 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="377d4-115">실행 어셈블리의 경우 로더가 [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 함수를 대신 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="377d4-116">운영 체제 로더는 DLL 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="377d4-117">운영 체제 로더에서는 `_CorDllMain` 함수를 직접 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="377d4-118">자세한 내용은 [CorValidateImage\_](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) 항목의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="377d4-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377d4-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="377d4-119">Requirements</span></span>  

 <span data-ttu-id="377d4-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="377d4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377d4-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="377d4-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="377d4-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="377d4-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="377d4-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377d4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377d4-124">참조</span><span class="sxs-lookup"><span data-stu-id="377d4-124">See also</span></span>

- [<span data-ttu-id="377d4-125">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="377d4-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
