---
title: IMetaDataImport2::GetMethodSpecProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
ms.openlocfilehash: 6b5b3b3b5a3613668f4470f48083ae010cc9d336
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445245"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="139fd-102">IMetaDataImport2::GetMethodSpecProps 메서드</span><span class="sxs-lookup"><span data-stu-id="139fd-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="139fd-103">지정 된 MethodSpec 토큰에서 참조 하는 메서드의 메타 데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="139fd-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="139fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="139fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="139fd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="139fd-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="139fd-106">진행 메서드의 인스턴스화를 나타내는 MethodSpec 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="139fd-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="139fd-107">제한이 메서드 정의를 나타내는 MethodDef 또는 MethodRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="139fd-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="139fd-108">제한이 메서드의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="139fd-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="139fd-109">제한이 `ppvSigBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="139fd-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="139fd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="139fd-110">Requirements</span></span>  
 <span data-ttu-id="139fd-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="139fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="139fd-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="139fd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="139fd-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="139fd-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="139fd-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="139fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="139fd-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="139fd-115">See also</span></span>

- [<span data-ttu-id="139fd-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="139fd-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="139fd-117">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="139fd-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
