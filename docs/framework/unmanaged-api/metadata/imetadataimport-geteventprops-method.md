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
ms.openlocfilehash: 18fe0c834506d0ac4cd15fd7af4c4f15904b0f81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437581"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="60029-102">IMetaDataImport::GetEventProps 메서드</span><span class="sxs-lookup"><span data-stu-id="60029-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="60029-103">선언 형식, 대리자에 대 한 추가 및 제거 메서드, 모든 플래그 및 기타 관련 데이터를 포함 하 여, 지정 된 이벤트 토큰이 나타내는 이벤트에 대 한 메타 데이터 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="60029-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60029-104">구문</span><span class="sxs-lookup"><span data-stu-id="60029-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="60029-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60029-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="60029-106">진행 메타 데이터를 가져올 이벤트를 나타내는 이벤트 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="60029-107">제한이 이벤트를 선언 하는 클래스를 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="60029-108">제한이 `ev`에서 참조 하는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="60029-109">진행 `szEvent`의 와이드 문자에서 요청 된 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="60029-110">제한이 `szEvent`의 와이드 문자에서 반환 되는 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="60029-111">제한이 이벤트의 <xref:System.Delegate> 형식을 나타내는 TypeRef 또는 TypeDef 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="60029-112">제한이 이벤트에 대 한 처리기를 추가 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="60029-113">제한이 이벤트에 대 한 처리기를 제거 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="60029-114">제한이 이벤트를 발생 시키는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="60029-115">제한이 이벤트와 연결 된 다른 메서드에 대 한 토큰 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="60029-116">[in] `rmdOtherMethod` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="60029-117">제한이 `rmdOtherMethod`에서 반환 된 토큰의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="60029-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60029-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60029-118">Requirements</span></span>  
 <span data-ttu-id="60029-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60029-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60029-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="60029-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60029-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60029-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60029-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60029-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60029-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="60029-123">See also</span></span>

- [<span data-ttu-id="60029-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60029-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="60029-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60029-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
