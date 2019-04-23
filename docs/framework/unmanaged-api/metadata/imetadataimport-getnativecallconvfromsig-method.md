---
title: IMetaDataImport::GetNativeCallConvFromSig 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef1ac83b383a9f6bbee7f55441d2abfcb081afa6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122748"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="e1513-102">IMetaDataImport::GetNativeCallConvFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="e1513-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="e1513-103">지정한 서명 포인터가 나타내는 메서드에 대한 기본 호출 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1513-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1513-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1513-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1513-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1513-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="e1513-106">[in] 에 대 한 호출 규칙을 반환 하는 메서드의 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1513-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="e1513-107">[in] 크기 (바이트) `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="e1513-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="e1513-108">[out] 네이티브 호출 규칙에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1513-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1513-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1513-109">Requirements</span></span>  
 <span data-ttu-id="e1513-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1513-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1513-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e1513-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1513-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e1513-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1513-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1513-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1513-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1513-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="e1513-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1513-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e1513-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1513-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
