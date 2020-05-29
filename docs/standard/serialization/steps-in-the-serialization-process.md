---
title: serialization 프로세스의 단계
description: Serialization 프로세스는 포맷터에서 Serialize 메서드가 호출될 때 시작됩니다. 이 문서에서는 이벤트의 순서를 설명합니다.
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: 1f749b9102182e78bc3fda436cf386a9f5759d5a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379096"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="95d52-104">serialization 프로세스의 단계</span><span class="sxs-lookup"><span data-stu-id="95d52-104">Steps in the serialization process</span></span>
<span data-ttu-id="95d52-105"><xref:System.Runtime.Serialization.Formatter.Serialize%2A> 메서드가 [포맷터](xref:System.Runtime.Serialization.Formatter)에서 호출되면 개체 serialization이 다음 규칙 시퀀스에 따라 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-105">When the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="95d52-106">포맷터에 서로게이트 선택기가 있는지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-106">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="95d52-107">포맷터에 서로게이트 선택기가 있는 경우에는 서로게이트 선택기가 지정된 형식의 개체를 처리하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-107">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="95d52-108">선택기가 개체 형식을 처리하는 경우에는 서로게이트 선택기에 대해 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-108">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="95d52-109">서로게이트 선택기가 없거나 개체 형식을 처리하지 않는 경우에는 개체가 [Serializable](xref:System.SerializableAttribute) 특성으로 표시되었는지 여부를 확인하는 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-109">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="95d52-110">개체가 해당 특성으로 표시되지 않은 경우 <xref:System.Runtime.Serialization.SerializationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-110">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="95d52-111">개체가 적절하게 표시된 경우에는 개체가 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하는지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-111">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="95d52-112">이 인터페이스를 구현하는 경우에는 개체에 대해 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-112">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> is called on the object.</span></span>
  
- <span data-ttu-id="95d52-113">개체가 <xref:System.Runtime.Serialization.ISerializable>을 구현하지 않는 경우에는 기본 serialization 정책이 사용되어 [NonSerialized](xref:System.NonSerializedAttribute)로 표시되지 않은 모든 필드를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="95d52-113">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="95d52-114">참조</span><span class="sxs-lookup"><span data-stu-id="95d52-114">See also</span></span>

- [<span data-ttu-id="95d52-115">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="95d52-115">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="95d52-116">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="95d52-116">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
