---
description: '자세히 알아보기: ICLRMetadataLocator:: GetMetadata 메서드'
title: ICLRMetadataLocator::GetMetadata 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: 4a7e8b906b66c4295dd24800d260790526114701
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772618"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="cc4fc-103">ICLRMetadataLocator::GetMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="cc4fc-103">ICLRMetadataLocator::GetMetadata Method</span></span>

<span data-ttu-id="cc4fc-104">이미지의 메타 데이터를 검색 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-104">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc4fc-105">구문</span><span class="sxs-lookup"><span data-stu-id="cc4fc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc4fc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc4fc-106">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="cc4fc-107">진행 이미지 파일의 경로를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-107">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="cc4fc-108">진행 이미지 파일의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-108">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="cc4fc-109">진행 이미지 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-109">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="cc4fc-110">진행 이미지의 guid (globally unique identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-110">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="cc4fc-111">진행 메타 데이터의 RVA (상대 가상 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-111">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="cc4fc-112">주소는 이미지 기준 주소를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-112">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="cc4fc-113">진행 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-113">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="cc4fc-114">진행 메타 데이터를 저장할 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-114">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="cc4fc-115">제한이 메타 데이터를 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-115">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="cc4fc-116">제한이 반환 되는 메타 데이터의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-116">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc4fc-117">설명</span><span class="sxs-lookup"><span data-stu-id="cc4fc-117">Remarks</span></span>  

 <span data-ttu-id="cc4fc-118">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-118">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc4fc-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc4fc-119">Requirements</span></span>  

 <span data-ttu-id="cc4fc-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc4fc-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc4fc-121">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="cc4fc-121">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cc4fc-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc4fc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc4fc-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc4fc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc4fc-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc4fc-124">See also</span></span>

- [<span data-ttu-id="cc4fc-125">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc4fc-125">ICLRMetadataLocator Interface</span></span>](iclrmetadatalocator-interface.md)
