---
title: ICorDebugILFrame2::EnumerateTypeParameters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 715ff5d4a06b53361d550f04e5154023d0b641bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095116"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="7b7eb-102">ICorDebugILFrame2::EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="7b7eb-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="7b7eb-103">이 프레임의 <xref:System.Type> 매개 변수를 포함 하는 ICorDebugTypeEnum 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b7eb-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b7eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b7eb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b7eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b7eb-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="7b7eb-106">형식 매개 변수를 열거할 수 있도록 하는 ICorDebugTypeEnum interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b7eb-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="7b7eb-107">형식 매개 변수 목록에는 클래스 형식 매개 변수 (있는 경우)와 메서드 형식 매개 변수 (있는 경우)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b7eb-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b7eb-108">주의</span><span class="sxs-lookup"><span data-stu-id="7b7eb-108">Remarks</span></span>  
 <span data-ttu-id="7b7eb-109">[IMetaDataImport2:: EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) 메서드를 사용 하 여이 목록에 포함 된 클래스 형식 매개 변수 및 메서드 형식 매개 변수의 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7eb-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="7b7eb-110">형식 매개 변수는 항상 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7b7eb-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b7eb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b7eb-111">Requirements</span></span>  
 <span data-ttu-id="7b7eb-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b7eb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b7eb-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b7eb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b7eb-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b7eb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b7eb-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b7eb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
