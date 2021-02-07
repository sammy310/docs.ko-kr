---
description: _CorExeMain 함수에 대해 자세히 알아보세요.
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
ms.openlocfilehash: f94197598d01255c35712aa682f83ca9be1fb377
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717136"
---
# <a name="_corexemain-function"></a><span data-ttu-id="52aac-103">_CorExeMain 함수</span><span class="sxs-lookup"><span data-stu-id="52aac-103">_CorExeMain Function</span></span>

<span data-ttu-id="52aac-104">CLR (공용 언어 런타임)을 초기화 하 고, 실행 가능한 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="52aac-104">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52aac-105">구문</span><span class="sxs-lookup"><span data-stu-id="52aac-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="52aac-106">설명</span><span class="sxs-lookup"><span data-stu-id="52aac-106">Remarks</span></span>  

 <span data-ttu-id="52aac-107">이 함수는 관리 되는 실행 어셈블리에서 만든 프로세스의 로더에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52aac-107">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="52aac-108">DLL 어셈블리의 경우 로더는 대신 [_CorDllMain](cordllmain-function.md) 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="52aac-108">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="52aac-109">운영 체제 로더는 이미지 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="52aac-109">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="52aac-110">Windows 98, Windows ME, Windows NT 및 Windows 2000에서 `_CorExeMain` 함수는 운영 체제 로더에서 픽스업을 통해 간접적으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52aac-110">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="52aac-111">다른 모든 버전의 Windows에서는 운영 체제 로더에서 직접 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="52aac-111">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="52aac-112">자세한 내용은 [_CorValidateImage](corvalidateimage-function.md) 항목의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="52aac-112">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52aac-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52aac-113">Requirements</span></span>  

 <span data-ttu-id="52aac-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52aac-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52aac-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="52aac-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52aac-116">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52aac-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52aac-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52aac-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52aac-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52aac-118">See also</span></span>

- [<span data-ttu-id="52aac-119">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="52aac-119">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
