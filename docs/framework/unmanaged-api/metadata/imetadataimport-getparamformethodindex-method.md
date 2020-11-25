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
ms.openlocfilehash: d4d3ba5713398876b55c072f0cda7eb5d599c4d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729288"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="ebf14-102">IMetaDataImport::GetParamForMethodIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="ebf14-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>

<span data-ttu-id="ebf14-103">지정 된 MethodDef 토큰이 나타내는 메서드의 지정 된 매개 변수를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ebf14-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf14-104">구문</span><span class="sxs-lookup"><span data-stu-id="ebf14-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebf14-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebf14-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="ebf14-106">진행 매개 변수 토큰을 반환할 메서드를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf14-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="ebf14-107">진행 매개 변수 목록에서 요청 된 매개 변수가 발생 하는 서 수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf14-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="ebf14-108">매개 변수의 번호는 1부터 시작 하며 메서드의 반환 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf14-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="ebf14-109">제한이 요청 된 매개 변수를 나타내는 ParamDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf14-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf14-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ebf14-110">Requirements</span></span>  

 <span data-ttu-id="ebf14-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebf14-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf14-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ebf14-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ebf14-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebf14-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ebf14-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf14-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf14-115">참조</span><span class="sxs-lookup"><span data-stu-id="ebf14-115">See also</span></span>

- [<span data-ttu-id="ebf14-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebf14-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ebf14-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebf14-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
