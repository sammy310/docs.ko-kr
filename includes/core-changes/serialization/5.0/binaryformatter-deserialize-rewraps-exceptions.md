---
ms.openlocfilehash: 4aef35502fc93cbf0399e3c8d0932338829d6c07
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517357"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="eb3f2-101">BinaryFormatter.Deserialize가 SerializationException에서 일부 예외를 다시 래핑</span><span class="sxs-lookup"><span data-stu-id="eb3f2-101">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="eb3f2-102">이제 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> 메서드는 예외를 호출자에게 전파하기 전에 <xref:System.Runtime.Serialization.SerializationException> 내부에서 일부 예외 개체를 다시 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f2-102">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

#### <a name="change-description"></a><span data-ttu-id="eb3f2-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="eb3f2-103">Change description</span></span>

<span data-ttu-id="eb3f2-104">이전에는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> 메서드가 <xref:System.ArgumentNullException> 같은 임의 예외에서 스택을 호출자에게 전파하도록 허용했습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f2-104">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="eb3f2-105">.NET 5.0 이상에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> 메서드는 잘못된 deserialization 작업으로 인해 발생하는 예외를 더 적극적으로 catch하여 <xref:System.Runtime.Serialization.SerializationException>에 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f2-105">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eb3f2-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="eb3f2-106">Version introduced</span></span>

<span data-ttu-id="eb3f2-107">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="eb3f2-107">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eb3f2-108">권장 조치</span><span class="sxs-lookup"><span data-stu-id="eb3f2-108">Recommended action</span></span>

<span data-ttu-id="eb3f2-109">대부분의 경우 아무 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f2-109">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="eb3f2-110">그러나 호출 사이트가 throw되는 특정 예외에 종속된 경우 다음 예제와 같이 외부 <xref:System.Runtime.Serialization.SerializationException>에서 예외를 래핑 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f2-110">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx)
{
    if (serEx.InnerException is MyException myEx)
    {
        // Handle 'myEx' here in case it was wrapped in SerializationException.
    }
    else
    {
        throw;
    }
}
```

#### <a name="category"></a><span data-ttu-id="eb3f2-111">범주</span><span class="sxs-lookup"><span data-stu-id="eb3f2-111">Category</span></span>

<span data-ttu-id="eb3f2-112">Serialization</span><span class="sxs-lookup"><span data-stu-id="eb3f2-112">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eb3f2-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="eb3f2-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->
