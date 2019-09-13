---
title: GUID_ManagedName 특성
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14d00f17a61576a50e26d3cbcf734a10ed3c03a
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895010"
---
# <a name="guid_managedname-attribute"></a><span data-ttu-id="32a06-102">GUID_ManagedName 특성</span><span class="sxs-lookup"><span data-stu-id="32a06-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="32a06-103">COM (구성 요소 개체 모델) 라이브러리의 관리 되는 네임 스페이스 이름을 지정 하는 사용자 지정 인터페이스 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="32a06-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a06-104">구문</span><span class="sxs-lookup"><span data-stu-id="32a06-104">Syntax</span></span>  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="32a06-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32a06-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="32a06-106">라이브러리에 대 한 관리 되는 네임 스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32a06-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="32a06-107">정의</span><span class="sxs-lookup"><span data-stu-id="32a06-107">Definition</span></span>  
 <span data-ttu-id="32a06-108">`GUID_ManagedName`는 다음과 같이 Cor에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32a06-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="32a06-109">설명</span><span class="sxs-lookup"><span data-stu-id="32a06-109">Remarks</span></span>  
 <span data-ttu-id="32a06-110">사용자 지정 인터페이스 특성은 형식 라이브러리의 개체에 대 한 메타 데이터를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="32a06-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="32a06-111">특성 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> 에서 <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> 관리 되는 이름을 검색 하려면 또는를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32a06-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="32a06-112">자세한 내용은 시각적 C++ 참조 설명서의 [인터페이스 특성](/cpp/windows/attributes/interface-attributes) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32a06-112">For more information, see [Interface Attributes](/cpp/windows/attributes/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32a06-113">예제</span><span class="sxs-lookup"><span data-stu-id="32a06-113">Example</span></span>  
 <span data-ttu-id="32a06-114">다음 예제에서는 특성을 `GUID_ManagedName` 사용 하는 라이브러리 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32a06-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
```idl
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="32a06-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32a06-115">Requirements</span></span>  
 <span data-ttu-id="32a06-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="32a06-116">**Header:** Cor.h</span></span>
