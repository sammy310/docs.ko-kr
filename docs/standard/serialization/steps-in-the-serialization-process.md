---
title: serialization 프로세스의 단계
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: b697e8c590d0865b26eaa9f66a333504a5faece2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954052"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="53a99-102">serialization 프로세스의 단계</span><span class="sxs-lookup"><span data-stu-id="53a99-102">Steps in the serialization process</span></span>
<span data-ttu-id="53a99-103"><xref:System.Runtime.Serialization.Formatter.Serialize*> 메서드가 [포맷터](xref:System.Runtime.Serialization.Formatter)에서 호출되면 개체 serialization이 다음 규칙 시퀀스에 따라 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-103">When the <xref:System.Runtime.Serialization.Formatter.Serialize*> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="53a99-104">포맷터에 서로게이트 선택기가 있는지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-104">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="53a99-105">포맷터에 서로게이트 선택기가 있는 경우에는 서로게이트 선택기가 지정된 형식의 개체를 처리하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-105">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="53a99-106">선택기가 개체 형식을 처리하는 경우에는 서로게이트 선택기에 대해 <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-106">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="53a99-107">서로게이트 선택기가 없거나 개체 형식을 처리하지 않는 경우에는 개체가 [Serializable](xref:System.SerializableAttribute) 특성으로 표시되었는지 여부를 확인하는 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-107">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="53a99-108">개체가 해당 특성으로 표시되지 않은 경우 <xref:System.Runtime.Serialization.SerializationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-108">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="53a99-109">개체가 적절하게 표시된 경우에는 개체가 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하는지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-109">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="53a99-110">이 인터페이스를 구현하는 경우에는 개체에 대해 <xref:System.Runtime.Serialization.ISerializable.GetObjectData*>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-110">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> is called on the object.</span></span>
  
- <span data-ttu-id="53a99-111">개체가 <xref:System.Runtime.Serialization.ISerializable>을 구현하지 않는 경우에는 기본 serialization 정책이 사용되어 [NonSerialized](xref:System.NonSerializedAttribute)로 표시되지 않은 모든 필드를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="53a99-111">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="53a99-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="53a99-112">See also</span></span>

- [<span data-ttu-id="53a99-113">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="53a99-113">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="53a99-114">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="53a99-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
