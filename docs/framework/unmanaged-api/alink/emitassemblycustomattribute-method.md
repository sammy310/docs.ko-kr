---
title: EmitAssemblyCustomAttribute 메서드
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69914bce7ed322d90cfbd03dd611e2b745dfe066
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470040"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="a858d-102">EmitAssemblyCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="a858d-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="a858d-103">어셈블리 수준 사용자 지정 특성을 설정 하려면 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a858d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a858d-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a858d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a858d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a858d-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a858d-107">특성을 정의 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-107">File that defiles the attribute.</span></span> <span data-ttu-id="a858d-108">NULL 일 수 `AssemblyID` 는 바인딩되지 않은 netmodule를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="a858d-109">사용자 지정 특성의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="a858d-110">사용자 지정 값 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="a858d-111">사용자 지정 값 데이터의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="a858d-112">사용자 지정 특성 서명 하는 어셈블리와 관련 되어 있으면 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="a858d-113">TRUE 이면 특성이 여러 개를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a858d-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="a858d-114">Return Value</span></span>  
 <span data-ttu-id="a858d-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a858d-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a858d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a858d-116">Requirements</span></span>  
 <span data-ttu-id="a858d-117">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="a858d-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a858d-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a858d-118">See also</span></span>
- [<span data-ttu-id="a858d-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a858d-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a858d-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a858d-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a858d-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="a858d-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
