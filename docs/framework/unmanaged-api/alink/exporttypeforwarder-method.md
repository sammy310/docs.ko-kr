---
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
ms.openlocfilehash: 4e6ceabf37056bfc25247266be2c7801cb0e13e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684774"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="3fb32-102">ExportTypeForwarder 메서드</span><span class="sxs-lookup"><span data-stu-id="3fb32-102">ExportTypeForwarder Method</span></span>

<span data-ttu-id="3fb32-103">지정 된 어셈블리의 형식 테이블에 형식 전달자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb32-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb32-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fb32-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fb32-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fb32-105">Parameters</span></span>  

 `tkAssemblyRef`  
 <span data-ttu-id="3fb32-106">형식 전달 자가 참조 하는 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb32-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="3fb32-107">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb32-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3fb32-108">`ComType` 또는와 같은 `tdPublic` 플래그 `tdNested` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb32-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="3fb32-109">이 값은 [DefineExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb32-109">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="3fb32-110">내보낸 형식의 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb32-110">Receives the token of the exported type.</span></span> <span data-ttu-id="3fb32-111">중첩 된 형식을 내보내는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb32-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fb32-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="3fb32-112">Return Value</span></span>  

 <span data-ttu-id="3fb32-113">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb32-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb32-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fb32-114">Requirements</span></span>  

 <span data-ttu-id="3fb32-115">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="3fb32-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb32-116">참조</span><span class="sxs-lookup"><span data-stu-id="3fb32-116">See also</span></span>

- [<span data-ttu-id="3fb32-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fb32-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3fb32-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fb32-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3fb32-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="3fb32-119">ALink API</span></span>](index.md)
