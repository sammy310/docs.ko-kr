---
description: _CorDllMain 함수에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 442afae3a627eb684a86c02fbc6e546aa804b7a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717151"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="5c753-103">\_CorDllMain 함수</span><span class="sxs-lookup"><span data-stu-id="5c753-103">\_CorDllMain Function</span></span>

<span data-ttu-id="5c753-104">CLR (공용 언어 런타임)을 초기화 하 고, DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-104">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c753-105">구문</span><span class="sxs-lookup"><span data-stu-id="5c753-105">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c753-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c753-106">Parameters</span></span>  

 `hInst`  
 <span data-ttu-id="5c753-107">진행 로드 된 모듈의 인스턴스 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-107">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="5c753-108">진행 DLL 진입점 함수가 호출 되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-108">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="5c753-109">이 매개 변수는 다음 값 중 하나일 수 있습니다. DLL \_ PROCESS_ATTACH, dll \_ 스레드 \_ 연결, dll \_ 스레드 \_ 연결 또는 dll \_ 프로세스 \_ 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-109">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="5c753-110">이러한 값에 대 한 설명은 `DllMain` PLATFORM SDK의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c753-110">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="5c753-111">진행 사용 되지 않는.</span><span class="sxs-lookup"><span data-stu-id="5c753-111">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c753-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="5c753-112">Return Value</span></span>  

 <span data-ttu-id="5c753-113">이 메서드 `true` 는 성공에 대해를 반환 하 고 `false` 오류가 발생 하면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-113">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c753-114">설명</span><span class="sxs-lookup"><span data-stu-id="5c753-114">Remarks</span></span>  

 <span data-ttu-id="5c753-115">이 함수는 DLL 어셈블리에 대 한 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-115">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="5c753-116">실행 어셈블리의 경우 로더가 대신 [ \_ CorExeMain](corexemain-function.md) 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-116">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="5c753-117">운영 체제 로더는 DLL 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-117">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="5c753-118">`_CorDllMain`함수는 운영 체제 로더에서 직접 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-118">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="5c753-119">자세한 내용은 [ \_ corvalidateimage](corvalidateimage-function.md) 항목의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c753-119">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c753-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c753-120">Requirements</span></span>  

 <span data-ttu-id="5c753-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c753-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c753-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="5c753-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c753-123">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c753-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c753-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c753-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c753-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c753-125">See also</span></span>

- [<span data-ttu-id="5c753-126">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5c753-126">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
