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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f70187ba9bd71225162e6e10184e4992b5600f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645164"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="b6464-102">IMetaDataTables2::GetMetaDataStreamInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b6464-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="b6464-103">이름, 크기 및 지정된 된 인덱스에서 메타 데이터 스트림의 내용을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6464-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6464-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6464-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6464-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6464-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="b6464-106">[in] 요청 된 메타 데이터 스트림 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="b6464-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="b6464-107">[out] 스트림의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6464-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="b6464-108">[out] 메타 데이터 스트림에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6464-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="b6464-109">[out] 크기 (바이트)의 `ppv`합니다.</span><span class="sxs-lookup"><span data-stu-id="b6464-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6464-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6464-110">Requirements</span></span>  
 <span data-ttu-id="b6464-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6464-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6464-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b6464-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6464-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b6464-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6464-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6464-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6464-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6464-115">See also</span></span>

- [<span data-ttu-id="b6464-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6464-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="b6464-117">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6464-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
