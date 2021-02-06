---
description: '자세히 알아보기: EmitAssemblyCustomAttribute 메서드'
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
ms.openlocfilehash: c91eb563c14b442a22db8f328287c10e5cc9a63c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638329"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="79918-103">EmitAssemblyCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="79918-103">EmitAssemblyCustomAttribute Method</span></span>

<span data-ttu-id="79918-104">을 호출 하 여 어셈블리 수준 사용자 지정 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79918-104">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79918-105">구문</span><span class="sxs-lookup"><span data-stu-id="79918-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="79918-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79918-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="79918-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="79918-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="79918-108">특성의 파일을 제거 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="79918-108">File that defiles the attribute.</span></span> <span data-ttu-id="79918-109">`AssemblyID`가 바인딩되지 않은 .netmodule을 나타내지 않는 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79918-109">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="79918-110">사용자 지정 특성의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="79918-110">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="79918-111">사용자 지정 값 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="79918-111">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="79918-112">사용자 지정 값 데이터의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="79918-112">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="79918-113">사용자 지정 특성이 어셈블리 서명과 관련 되어 있으면 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="79918-113">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="79918-114">여러 특성을 내보내야 하는 경우 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="79918-114">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79918-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="79918-115">Return Value</span></span>  

 <span data-ttu-id="79918-116">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79918-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79918-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79918-117">Requirements</span></span>  

 <span data-ttu-id="79918-118">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="79918-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79918-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79918-119">See also</span></span>

- [<span data-ttu-id="79918-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79918-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="79918-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79918-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="79918-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="79918-122">ALink API</span></span>](index.md)
