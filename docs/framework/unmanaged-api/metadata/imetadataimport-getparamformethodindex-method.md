---
title: IMetaDataImport::GetParamForMethodIndex 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdb3def9574f4442a22b370323dfdf044170542b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778936"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="8d0ec-102">IMetaDataImport::GetParamForMethodIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="8d0ec-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="8d0ec-103">지정한 MethodDef 토큰이 나타내는 메서드의 지정 된 매개 변수를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d0ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d0ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d0ec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8d0ec-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="8d0ec-106">[in] 에 대 한 매개 변수 토큰을 반환 하도록 메서드를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="8d0ec-107">[in] 발생 하는 요청 된 매개 변수는 매개 변수 목록의 서 수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="8d0ec-108">매개 변수는 위치 0에에서 메서드의 반환 값을 사용 하 여 하나에서 시작 하는 번호가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="8d0ec-109">[out] 요청 된 매개 변수를 나타내는 ParamDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d0ec-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d0ec-110">Requirements</span></span>  
 <span data-ttu-id="8d0ec-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d0ec-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d0ec-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d0ec-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8d0ec-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8d0ec-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d0ec-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0ec-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="8d0ec-115">See also</span></span>

- [<span data-ttu-id="8d0ec-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d0ec-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8d0ec-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d0ec-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
