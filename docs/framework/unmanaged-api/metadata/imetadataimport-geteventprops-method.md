---
title: IMetaDataImport::GetEventProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f2eec9fce1909f6a83190f5ba3e99162461bbc4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492155"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="35c46-102">IMetaDataImport::GetEventProps 메서드</span><span class="sxs-lookup"><span data-stu-id="35c46-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="35c46-103">선언 형식, 추가 및 제거 메서드를 대리자에 대해 플래그 및 기타 관련된 데이터를 포함 하 여, 지정한 이벤트 토큰이 나타내는 이벤트에 대 한 메타 데이터 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35c46-104">구문</span><span class="sxs-lookup"><span data-stu-id="35c46-104">Syntax</span></span>  
  
```  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35c46-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35c46-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="35c46-106">[in] 이벤트 메타 데이터에 대 한 메타 데이터를 가져올 이벤트를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="35c46-107">[out] 이벤트를 선언 하는 클래스를 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="35c46-108">[out] 참조 하는 이벤트의 이름을 `ev`입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="35c46-109">[in] 요청된 된 길이의 와이드 문자 `szEvent`합니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="35c46-110">[out] 와이드 문자에서는 반환 된 길이 `szEvent`입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="35c46-111">[out] TypeRef 또는 TypeDef 메타 데이터 토큰을 나타내는에 대 한 포인터를 <xref:System.Delegate> 이벤트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="35c46-112">[out] 이벤트 처리기를 추가 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="35c46-113">[out] 이벤트 처리기를 제거 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="35c46-114">[out] 이벤트를 발생 시키는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="35c46-115">[out] 이벤트와 연결 된 다른 메서드를 토큰 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="35c46-116">[in] `rmdOtherMethod` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="35c46-117">[out] 반환 된 토큰 수 `rmdOtherMethod`입니다.</span><span class="sxs-lookup"><span data-stu-id="35c46-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35c46-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35c46-118">Requirements</span></span>  
 <span data-ttu-id="35c46-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="35c46-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35c46-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35c46-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35c46-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="35c46-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35c46-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35c46-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35c46-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="35c46-123">See also</span></span>
- [<span data-ttu-id="35c46-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35c46-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="35c46-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35c46-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
