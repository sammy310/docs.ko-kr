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
ms.openlocfilehash: 369335deb67d74ee3cb9fa407533e40716aa3a3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676866"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="1e991-102">IMetaDataImport::GetEventProps 메서드</span><span class="sxs-lookup"><span data-stu-id="1e991-102">IMetaDataImport::GetEventProps Method</span></span>

<span data-ttu-id="1e991-103">선언 형식, 대리자에 대 한 추가 및 제거 메서드, 모든 플래그 및 기타 관련 데이터를 포함 하 여, 지정 된 이벤트 토큰이 나타내는 이벤트에 대 한 메타 데이터 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e991-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e991-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1e991-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e991-105">Parameters</span></span>  

 `ev`  
 <span data-ttu-id="1e991-106">진행 메타 데이터를 가져올 이벤트를 나타내는 이벤트 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="1e991-107">제한이 이벤트를 선언 하는 클래스를 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="1e991-108">제한이 에서 참조 하는 이벤트의 이름 `ev` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="1e991-109">진행 의 와이드 문자에서 요청 된 길이입니다 `szEvent` .</span><span class="sxs-lookup"><span data-stu-id="1e991-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="1e991-110">제한이 의 와이드 문자에서 반환 되는 길이입니다 `szEvent` .</span><span class="sxs-lookup"><span data-stu-id="1e991-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="1e991-111">제한이 이벤트 유형을 나타내는 TypeRef 또는 TypeDef 메타 데이터 토큰에 대 한 포인터 <xref:System.Delegate> 입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="1e991-112">제한이 이벤트에 대 한 처리기를 추가 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="1e991-113">제한이 이벤트에 대 한 처리기를 제거 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="1e991-114">제한이 이벤트를 발생 시키는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="1e991-115">제한이 이벤트와 연결 된 다른 메서드에 대 한 토큰 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1e991-116">[in] `rmdOtherMethod` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="1e991-117">제한이 에서 반환 된 토큰의 수 `rmdOtherMethod` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e991-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e991-118">Requirements</span></span>  

 <span data-ttu-id="1e991-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e991-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e991-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1e991-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e991-121">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e991-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e991-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e991-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e991-123">참조</span><span class="sxs-lookup"><span data-stu-id="1e991-123">See also</span></span>

- [<span data-ttu-id="1e991-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e991-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1e991-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e991-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
