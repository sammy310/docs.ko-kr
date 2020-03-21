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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177263"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="3eb96-102">IMetaDataImport::GetEventProps 메서드</span><span class="sxs-lookup"><span data-stu-id="3eb96-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="3eb96-103">선언 유형, 대리자에 대한 추가 및 제거 메서드, 플래그 및 기타 관련 데이터를 포함하여 지정된 이벤트 토큰으로 표시되는 이벤트에 대한 메타데이터 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb96-104">구문</span><span class="sxs-lookup"><span data-stu-id="3eb96-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3eb96-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3eb96-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="3eb96-106">【인】 이벤트를 나타내는 이벤트 메타데이터 토큰으로 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="3eb96-107">【아웃】 이벤트를 선언하는 클래스를 나타내는 TypeDef 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="3eb96-108">【아웃】 에서 참조하는 이벤트의 이름입니다. `ev`</span><span class="sxs-lookup"><span data-stu-id="3eb96-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="3eb96-109">【인】 의 넓은 문자로 `szEvent`요청된 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="3eb96-110">【아웃】 의 넓은 문자로 `szEvent`반환 된 길이 .</span><span class="sxs-lookup"><span data-stu-id="3eb96-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="3eb96-111">【아웃】 이벤트 유형을 나타내는 TypeRef 또는 TypeDef <xref:System.Delegate> 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="3eb96-112">【아웃】 이벤트에 대한 처리기를 추가하는 메서드를 나타내는 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="3eb96-113">【아웃】 이벤트에 대 한 처리기를 제거 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="3eb96-114">【아웃】 이벤트를 발생 시키는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="3eb96-115">【아웃】 이벤트와 관련된 다른 메서드에 대한 토큰 포인터 의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3eb96-116">[in] `rmdOtherMethod` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="3eb96-117">【아웃】 에서 반환되는 토큰 `rmdOtherMethod`수입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb96-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb96-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3eb96-118">Requirements</span></span>  
 <span data-ttu-id="3eb96-119">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3eb96-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb96-120">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="3eb96-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3eb96-121">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3eb96-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3eb96-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb96-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb96-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3eb96-123">See also</span></span>

- [<span data-ttu-id="3eb96-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3eb96-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3eb96-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3eb96-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
