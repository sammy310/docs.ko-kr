---
title: ICLRDataTarget::GetImageBase 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: 71b07e11cd3fec1a0dbebe986d98067c2e6f18e1
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860636"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="b1639-102">ICLRDataTarget::GetImageBase 메서드</span><span class="sxs-lookup"><span data-stu-id="b1639-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="b1639-103">지정 된 이미지의 기본 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1639-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1639-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1639-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1639-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1639-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="b1639-106">진행 경로를 포함 하는 이미지의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b1639-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="b1639-107">제한이 이미지의 기준 주소를 저장 하는 CLRDATA_ADDRESS에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1639-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1639-108">설명</span><span class="sxs-lookup"><span data-stu-id="b1639-108">Remarks</span></span>  
 <span data-ttu-id="b1639-109">이미지 파일 이름에 경로가 있을 수도 있고 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1639-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="b1639-110">경로를 지정 하면 전체 경로에서 일치가 수행 됩니다. 그렇지 않으면 파일 이름에 대해서만 일치가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1639-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1639-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1639-111">Requirements</span></span>  
 <span data-ttu-id="b1639-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1639-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1639-113">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="b1639-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b1639-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1639-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1639-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1639-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1639-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1639-116">See also</span></span>

- [<span data-ttu-id="b1639-117">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1639-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
