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
ms.openlocfilehash: ec0a86e3396ad42152bc0a244f74ad13deba16e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446511"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="068fb-102">EmitAssemblyCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="068fb-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="068fb-103">을 호출 하 여 어셈블리 수준 사용자 지정 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="068fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="068fb-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="068fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="068fb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="068fb-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="068fb-107">특성의 파일을 제거 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-107">File that defiles the attribute.</span></span> <span data-ttu-id="068fb-108">`AssemblyID`에서 바인딩되지 않은 .netmodule을 나타내지 않는 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="068fb-109">사용자 지정 특성의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="068fb-110">사용자 지정 값 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="068fb-111">사용자 지정 값 데이터의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="068fb-112">사용자 지정 특성이 어셈블리 서명과 관련 되어 있으면 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="068fb-113">여러 특성을 내보내야 하는 경우 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="068fb-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="068fb-114">Return Value</span></span>  
 <span data-ttu-id="068fb-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="068fb-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="068fb-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="068fb-116">Requirements</span></span>  
 <span data-ttu-id="068fb-117">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="068fb-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068fb-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="068fb-118">See also</span></span>

- [<span data-ttu-id="068fb-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="068fb-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="068fb-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="068fb-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="068fb-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="068fb-121">ALink API</span></span>](index.md)
