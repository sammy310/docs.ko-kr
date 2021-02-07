---
description: _CorExeMain2 함수에 대해 자세히 알아보세요.
title: _CorExeMain2 함수
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
ms.openlocfilehash: 4629ea2f6c2ba13351c409bc382077eea926b507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717110"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="e1048-103">_CorExeMain2 함수</span><span class="sxs-lookup"><span data-stu-id="e1048-103">_CorExeMain2 Function</span></span>

<span data-ttu-id="e1048-104">지정 된 메모리 매핑된 코드에서 진입점을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1048-104">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="e1048-105">이 함수는 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1048-105">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1048-106">구문</span><span class="sxs-lookup"><span data-stu-id="e1048-106">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1048-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1048-107">Parameters</span></span>  

 `pUnmappedPE`  
 <span data-ttu-id="e1048-108">진행 메모리 매핑된 코드에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1048-108">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="e1048-109">진행 포함할 수 있는 요소 수 `pUnmappedPE` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e1048-109">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="e1048-110">진행 실행 가능 이미지의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1048-110">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="e1048-111">진행 로더 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e1048-111">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="e1048-112">진행 명령줄 매개 변수 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="e1048-112">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1048-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1048-113">Requirements</span></span>  

 <span data-ttu-id="e1048-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1048-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1048-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e1048-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1048-116">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1048-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1048-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1048-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1048-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1048-118">See also</span></span>

- [<span data-ttu-id="e1048-119">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="e1048-119">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
