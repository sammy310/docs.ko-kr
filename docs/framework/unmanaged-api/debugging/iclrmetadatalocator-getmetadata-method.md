---
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
ms.openlocfilehash: ad309290319396ff4e74e30d572effeffe802d1d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859882"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="ffb52-102">ICLRMetadataLocator::GetMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="ffb52-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="ffb52-103">이미지의 메타 데이터를 검색 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb52-104">구문</span><span class="sxs-lookup"><span data-stu-id="ffb52-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ffb52-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ffb52-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="ffb52-106">진행 이미지 파일의 경로를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="ffb52-107">진행 이미지 파일의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="ffb52-108">진행 이미지 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="ffb52-109">진행 이미지의 guid (globally unique identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="ffb52-110">진행 메타 데이터의 RVA (상대 가상 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="ffb52-111">주소는 이미지 기준 주소를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="ffb52-112">진행 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="ffb52-113">진행 메타 데이터를 저장할 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="ffb52-114">제한이 메타 데이터를 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="ffb52-115">제한이 반환 되는 메타 데이터의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffb52-116">설명</span><span class="sxs-lookup"><span data-stu-id="ffb52-116">Remarks</span></span>  
 <span data-ttu-id="ffb52-117">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb52-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffb52-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffb52-118">Requirements</span></span>  
 <span data-ttu-id="ffb52-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffb52-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffb52-120">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="ffb52-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ffb52-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffb52-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffb52-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffb52-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffb52-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffb52-123">See also</span></span>

- [<span data-ttu-id="ffb52-124">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffb52-124">ICLRMetadataLocator Interface</span></span>](iclrmetadatalocator-interface.md)
