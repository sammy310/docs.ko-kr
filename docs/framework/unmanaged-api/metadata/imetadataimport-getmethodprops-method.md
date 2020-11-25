---
title: IMetaDataImport::GetMethodProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 0eb4e9d713581cf32cec18bb02a6bd13542e517a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733187"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="71762-102">IMetaDataImport::GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="71762-102">IMetaDataImport::GetMethodProps Method</span></span>

<span data-ttu-id="71762-103">지정한 MethodDef 토큰이 참조하는 메서드와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71762-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71762-104">구문</span><span class="sxs-lookup"><span data-stu-id="71762-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71762-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71762-105">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="71762-106">진행 메타 데이터를 반환할 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="71762-107">제한이 메서드를 구현 하는 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="71762-108">제한이 메서드의 이름이 있는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="71762-109">진행 요청 된 크기 `szMethod` 입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="71762-110">제한이 의 와이드 문자 크기에 대 한 포인터 `szMethod` 이거나, 잘림 인 경우 메서드 이름에 있는 와이드 문자의 실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="71762-111">제한이 메서드와 연결 된 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="71762-112">제한이 메서드의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="71762-113">제한이 의 바이트 크기에 대 한 포인터입니다 `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="71762-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="71762-114">제한이 메서드의 상대 가상 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="71762-115">제한이 메서드에 대 한 구현 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71762-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71762-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71762-116">Requirements</span></span>  

 <span data-ttu-id="71762-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71762-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71762-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="71762-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71762-119">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71762-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71762-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71762-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71762-121">참조</span><span class="sxs-lookup"><span data-stu-id="71762-121">See also</span></span>

- [<span data-ttu-id="71762-122">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71762-122">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="71762-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71762-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
