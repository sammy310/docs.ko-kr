---
title: IMetaDataTables2::GetMetaDataStreamInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 7d39d089c348b7320651ed21ea14ba07d7877fd4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501097"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="ee311-102">IMetaDataTables2::GetMetaDataStreamInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="ee311-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="ee311-103">지정 된 인덱스에 있는 메타 데이터 스트림의 이름, 크기 및 내용을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee311-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee311-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee311-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee311-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ee311-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="ee311-106">진행 요청 된 메타 데이터 스트림의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="ee311-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="ee311-107">제한이 스트림 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ee311-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ee311-108">제한이 메타 데이터 스트림에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ee311-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="ee311-109">제한이 의 크기 (바이트)입니다 `ppv` .</span><span class="sxs-lookup"><span data-stu-id="ee311-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee311-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee311-110">Requirements</span></span>  
 <span data-ttu-id="ee311-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee311-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee311-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ee311-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee311-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee311-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee311-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee311-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee311-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee311-115">See also</span></span>

- [<span data-ttu-id="ee311-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee311-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="ee311-117">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee311-117">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
