---
description: 다음에 대해 자세히 알아보세요. ExportTypeForwarder 메서드
title: ExportTypeForwarder 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
ms.openlocfilehash: 59fb74c83f6d30dda87d908353795fb218190022
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637991"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="e0b8c-103">ExportTypeForwarder 메서드</span><span class="sxs-lookup"><span data-stu-id="e0b8c-103">ExportTypeForwarder Method</span></span>

<span data-ttu-id="e0b8c-104">지정 된 어셈블리의 형식 테이블에 형식 전달자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b8c-104">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b8c-105">구문</span><span class="sxs-lookup"><span data-stu-id="e0b8c-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0b8c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0b8c-106">Parameters</span></span>  

 `tkAssemblyRef`  
 <span data-ttu-id="e0b8c-107">형식 전달 자가 참조 하는 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b8c-107">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="e0b8c-108">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b8c-108">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e0b8c-109">`ComType` 또는와 같은 `tdPublic` 플래그 `tdNested` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e0b8c-109">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="e0b8c-110">이 값은 [DefineExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b8c-110">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="e0b8c-111">내보낸 형식의 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b8c-111">Receives the token of the exported type.</span></span> <span data-ttu-id="e0b8c-112">중첩 된 형식을 내보내는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b8c-112">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0b8c-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="e0b8c-113">Return Value</span></span>  

 <span data-ttu-id="e0b8c-114">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b8c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0b8c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0b8c-115">Requirements</span></span>  

 <span data-ttu-id="e0b8c-116">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="e0b8c-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b8c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0b8c-117">See also</span></span>

- [<span data-ttu-id="e0b8c-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0b8c-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e0b8c-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0b8c-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e0b8c-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="e0b8c-120">ALink API</span></span>](index.md)
