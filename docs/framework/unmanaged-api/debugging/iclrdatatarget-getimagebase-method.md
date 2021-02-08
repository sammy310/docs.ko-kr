---
description: '자세히 알아보기: ICLRDataTarget:: Ge Agebase 메서드'
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
ms.openlocfilehash: 34e8341b219aaa184b4894c631f854e0a31921d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794873"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="c7c1b-103">ICLRDataTarget::GetImageBase 메서드</span><span class="sxs-lookup"><span data-stu-id="c7c1b-103">ICLRDataTarget::GetImageBase Method</span></span>

<span data-ttu-id="c7c1b-104">지정 된 이미지의 기본 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c7c1b-104">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7c1b-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7c1b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7c1b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7c1b-106">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="c7c1b-107">진행 경로를 포함 하는 이미지의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c7c1b-107">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="c7c1b-108">제한이 이미지의 기준 주소를 저장 하는 CLRDATA_ADDRESS에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c7c1b-108">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7c1b-109">설명</span><span class="sxs-lookup"><span data-stu-id="c7c1b-109">Remarks</span></span>  

 <span data-ttu-id="c7c1b-110">이미지 파일 이름에 경로가 있을 수도 있고 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c1b-110">The image file name may or may not have a path.</span></span> <span data-ttu-id="c7c1b-111">경로를 지정 하면 전체 경로에서 일치가 수행 됩니다. 그렇지 않으면 파일 이름에 대해서만 일치가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7c1b-111">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7c1b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7c1b-112">Requirements</span></span>  

 <span data-ttu-id="c7c1b-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7c1b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7c1b-114">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="c7c1b-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c7c1b-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7c1b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7c1b-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7c1b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c1b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7c1b-117">See also</span></span>

- [<span data-ttu-id="c7c1b-118">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7c1b-118">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
