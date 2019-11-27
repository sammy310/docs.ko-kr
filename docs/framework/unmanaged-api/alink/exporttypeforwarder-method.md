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
ms.openlocfilehash: 36c99477e9faead5e24799d5b0ae8901f1dd13c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448712"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="5ec7b-102">ExportTypeForwarder 메서드</span><span class="sxs-lookup"><span data-stu-id="5ec7b-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="5ec7b-103">지정 된 어셈블리의 형식 테이블에 형식 전달자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ec7b-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ec7b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ec7b-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="5ec7b-106">형식 전달 자가 참조 하는 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="5ec7b-107">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5ec7b-108">`tdPublic` 또는 `tdNested`와 같은 플래그를 `ComType` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="5ec7b-109">이 값은 [DefineExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-109">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="5ec7b-110">내보낸 형식의 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-110">Receives the token of the exported type.</span></span> <span data-ttu-id="5ec7b-111">중첩 된 형식을 내보내는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ec7b-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="5ec7b-112">Return Value</span></span>  
 <span data-ttu-id="5ec7b-113">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ec7b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ec7b-114">Requirements</span></span>  
 <span data-ttu-id="5ec7b-115">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="5ec7b-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec7b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ec7b-116">See also</span></span>

- [<span data-ttu-id="5ec7b-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ec7b-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5ec7b-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ec7b-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5ec7b-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="5ec7b-119">ALink API</span></span>](index.md)
