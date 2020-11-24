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
ms.openlocfilehash: 1b3ebcabc66ee7ca29245bb02d958be311bc65fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673698"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="7c8c8-102">\_CorDllMain 함수</span><span class="sxs-lookup"><span data-stu-id="7c8c8-102">\_CorDllMain Function</span></span>

<span data-ttu-id="7c8c8-103">CLR (공용 언어 런타임)을 초기화 하 고, DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c8c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c8c8-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c8c8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c8c8-105">Parameters</span></span>  

 `hInst`  
 <span data-ttu-id="7c8c8-106">진행 로드 된 모듈의 인스턴스 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="7c8c8-107">진행 DLL 진입점 함수가 호출 되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="7c8c8-108">이 매개 변수는 다음 값 중 하나일 수 있습니다. DLL \_ PROCESS_ATTACH, dll \_ 스레드 \_ 연결, dll \_ 스레드 \_ 연결 또는 dll \_ 프로세스 \_ 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="7c8c8-109">이러한 값에 대 한 설명은 `DllMain` PLATFORM SDK의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="7c8c8-110">진행 사용 되지 않는.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c8c8-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7c8c8-111">Return Value</span></span>  

 <span data-ttu-id="7c8c8-112">이 메서드 `true` 는 성공에 대해를 반환 하 고 `false` 오류가 발생 하면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c8c8-113">설명</span><span class="sxs-lookup"><span data-stu-id="7c8c8-113">Remarks</span></span>  

 <span data-ttu-id="7c8c8-114">이 함수는 DLL 어셈블리에 대 한 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="7c8c8-115">실행 어셈블리의 경우 로더가 대신 [ \_ CorExeMain](corexemain-function.md) 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-115">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="7c8c8-116">운영 체제 로더는 DLL 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="7c8c8-117">`_CorDllMain`함수는 운영 체제 로더에서 직접 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="7c8c8-118">자세한 내용은 [ \_ corvalidateimage](corvalidateimage-function.md) 항목의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-118">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c8c8-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c8c8-119">Requirements</span></span>  

 <span data-ttu-id="7c8c8-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c8c8-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7c8c8-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c8c8-122">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c8c8-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c8c8-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c8c8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8c8-124">참조</span><span class="sxs-lookup"><span data-stu-id="7c8c8-124">See also</span></span>

- [<span data-ttu-id="7c8c8-125">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="7c8c8-125">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
