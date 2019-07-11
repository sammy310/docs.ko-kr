---
title: _CorExeMain 함수
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97e90e3953a01f07d77e604628fbdb79eb9efa0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779169"
---
# <a name="corexemain-function"></a><span data-ttu-id="71e5a-102">_CorExeMain 함수</span><span class="sxs-lookup"><span data-stu-id="71e5a-102">_CorExeMain Function</span></span>
<span data-ttu-id="71e5a-103">CLR (공용 언어 런타임)을 초기화 하 고 실행 가능한 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾습니다 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="71e5a-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e5a-104">구문</span><span class="sxs-lookup"><span data-stu-id="71e5a-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="71e5a-105">설명</span><span class="sxs-lookup"><span data-stu-id="71e5a-105">Remarks</span></span>  
 <span data-ttu-id="71e5a-106">이 함수는 관리 되는 실행 가능한 어셈블리에서 생성 된 프로세스에서 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e5a-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="71e5a-107">로더가 DLL 어셈블리에 대 한 호출을 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) 함수를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="71e5a-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="71e5a-108">운영 체제 로더는 이미지 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="71e5a-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="71e5a-109">Windows 98, Windows ME, Windows NT 및 Windows 2000에는 `_CorExeMain` 함수 픽스업에 운영 체제 로더를 통해 간접적으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e5a-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="71e5a-110">다른 모든 버전의 Windows에서는 운영 체제 로더에 의해 직접 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71e5a-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="71e5a-111">자세한 내용은 주의 섹션을 참조 합니다 [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="71e5a-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71e5a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71e5a-112">Requirements</span></span>  
 <span data-ttu-id="71e5a-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71e5a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71e5a-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71e5a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71e5a-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="71e5a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71e5a-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71e5a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e5a-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="71e5a-117">See also</span></span>

- [<span data-ttu-id="71e5a-118">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="71e5a-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
