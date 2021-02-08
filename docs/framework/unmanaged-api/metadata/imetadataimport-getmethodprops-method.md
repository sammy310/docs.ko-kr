---
description: '자세히 알아보기: IMetaDataImport:: GetMethodProps 메서드'
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
ms.openlocfilehash: 5fb344d72378a806e0e71820b55a90998e497916
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783883"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="272d4-103">IMetaDataImport::GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="272d4-103">IMetaDataImport::GetMethodProps Method</span></span>

<span data-ttu-id="272d4-104">지정한 MethodDef 토큰이 참조하는 메서드와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-104">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="272d4-105">구문</span><span class="sxs-lookup"><span data-stu-id="272d4-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="272d4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="272d4-106">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="272d4-107">진행 메타 데이터를 반환할 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-107">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="272d4-108">제한이 메서드를 구현 하는 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-108">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="272d4-109">제한이 메서드의 이름이 있는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-109">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="272d4-110">진행 요청 된 크기 `szMethod` 입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-110">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="272d4-111">제한이 의 와이드 문자 크기에 대 한 포인터 `szMethod` 이거나, 잘림 인 경우 메서드 이름에 있는 와이드 문자의 실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-111">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="272d4-112">제한이 메서드와 연결 된 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-112">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="272d4-113">제한이 메서드의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-113">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="272d4-114">제한이 의 바이트 크기에 대 한 포인터입니다 `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="272d4-114">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="272d4-115">제한이 메서드의 상대 가상 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-115">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="272d4-116">제한이 메서드에 대 한 구현 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-116">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="272d4-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="272d4-117">Requirements</span></span>  

 <span data-ttu-id="272d4-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="272d4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="272d4-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="272d4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="272d4-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="272d4-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="272d4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="272d4-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="272d4-122">See also</span></span>

- [<span data-ttu-id="272d4-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="272d4-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="272d4-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="272d4-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
