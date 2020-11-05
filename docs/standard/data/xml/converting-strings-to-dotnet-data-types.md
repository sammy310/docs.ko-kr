---
title: 문자열을 .NET 데이터 형식으로 변환
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: 28c84b04bde045643158d8d2b9fed44b74334e77
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92688009"
---
# <a name="convert-strings-to-net-data-types"></a><span data-ttu-id="b7a11-102">문자열을 .NET 데이터 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="b7a11-102">Convert strings to .NET data types</span></span>

<span data-ttu-id="b7a11-103">문자열을 .NET 데이터 형식으로 변환하려면 애플리케이션 요구 사항에 적합한 **XmlConvert** 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-103">If you want to convert a string to a .NET data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="b7a11-104">**XmlConvert** 클래스에서 사용 가능한 변환 메서드의 전체 목록은 <xref:System.Xml.XmlConvert>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7a11-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="b7a11-105">**ToString** 메서드에서 반환된 문자열은 전달된 데이터를 문자열 버전으로 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="b7a11-106">또한 여러 가지 .NET 형식이 **XmlConvert** 클래스를 사용하여 변환을 수행하지만, 관련 형식은 **System.Convert** 클래스에 있는 메서드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-106">Additionally, there are several .NET types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="b7a11-107">**XmlConvert** 클래스는 XSD(XML 스키마) 데이터 형식 사양을 준수하며, **XmlConvert** 가 매핑할 수 있는 데이터 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="b7a11-108">다음 표에서는 XSD(XML 스키마) 데이터 형식 매핑을 사용할 때 반환되는 .NET 데이터 형식 및 문자열 형식의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-108">The following table lists .NET data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="b7a11-109">관련 .NET 형식은 **System.Convert** 에 의해 처리될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-109">These .NET types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="b7a11-110">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="b7a11-110">.NET type</span></span>|<span data-ttu-id="b7a11-111">반환 문자열</span><span class="sxs-lookup"><span data-stu-id="b7a11-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="b7a11-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="b7a11-112">Boolean</span></span>|<span data-ttu-id="b7a11-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="b7a11-113">"true", "false"</span></span>|  
|<span data-ttu-id="b7a11-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="b7a11-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="b7a11-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="b7a11-115">"INF"</span></span>|  
|<span data-ttu-id="b7a11-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="b7a11-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="b7a11-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="b7a11-117">"-INF"</span></span>|  
|<span data-ttu-id="b7a11-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="b7a11-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="b7a11-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="b7a11-119">"INF"</span></span>|  
|<span data-ttu-id="b7a11-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="b7a11-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="b7a11-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="b7a11-121">"-INF"</span></span>|  
|<span data-ttu-id="b7a11-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="b7a11-122">DateTime</span></span>|<span data-ttu-id="b7a11-123">형식은 "yyyy-MM-ddTHH:mm:sszzzzzz" 및 해당 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="b7a11-124">Timespan</span><span class="sxs-lookup"><span data-stu-id="b7a11-124">Timespan</span></span>|<span data-ttu-id="b7a11-125">형식은 PnYnMnTnHnMnS입니다. 즉, `P2Y10M15DT10H30M20S`는 2년 10개월 15일 10시간 30분 20초의 지속 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b7a11-126">**ToString** 메서드를 사용하여 이 테이블에 나열된 특정 .NET 형식을 변환하는 경우, 반환되는 문자열의 형식은 기본 형식이 아니라 XSD(XML 스키마) 문자열 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-126">If converting any of the .NET types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="b7a11-127">**DateTime** 및 **Timespan** 의 값 형식은 다릅니다. 즉, **DateTime** 은 순간적인 시각을 나타내며 **TimeSpan** 은 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="b7a11-128">**DateTime** 및 **Timespan** 형식은 XSD(XML 스키마) 데이터 형식 사양에 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="b7a11-129">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="b7a11-129">For example:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 <span data-ttu-id="b7a11-130">**출력**</span><span class="sxs-lookup"><span data-stu-id="b7a11-130">**Output**</span></span>  
  
 <span data-ttu-id="b7a11-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="b7a11-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="b7a11-132">다음 코드는 정수를 문자열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-132">The following code converts an integer to a string:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 <span data-ttu-id="b7a11-133">**출력**</span><span class="sxs-lookup"><span data-stu-id="b7a11-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="b7a11-134">하지만 문자열을 **Boolean** , **Single** 또는 **Double** 로 변환하는 경우 반환되는 .NET 형식은 **System.Convert** 클래스를 사용하는 경우의 반환 형식과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-134">However, if you are converting a string to **Boolean** , **Single** , or **Double** , the .NET type that's returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="b7a11-135">문자열을 Boolean 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="b7a11-135">String to Boolean</span></span>  
 <span data-ttu-id="b7a11-136">다음 표에서는 **ToBoolean** 메서드를 사용하여 문자열을 **Boolean** 으로 변환하는 경우 지정된 입력 문자열에 대해 생성되는 형식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="b7a11-137">유효한 문자열 입력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7a11-137">Valid string input parameter</span></span>|<span data-ttu-id="b7a11-138">.NET 출력 형식</span><span class="sxs-lookup"><span data-stu-id="b7a11-138">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="b7a11-139">"true"</span><span class="sxs-lookup"><span data-stu-id="b7a11-139">"true"</span></span>|<span data-ttu-id="b7a11-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="b7a11-140">Boolean.True</span></span>|  
|<span data-ttu-id="b7a11-141">"1"</span><span class="sxs-lookup"><span data-stu-id="b7a11-141">"1"</span></span>|<span data-ttu-id="b7a11-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="b7a11-142">Boolean.True</span></span>|  
|<span data-ttu-id="b7a11-143">"false"</span><span class="sxs-lookup"><span data-stu-id="b7a11-143">"false"</span></span>|<span data-ttu-id="b7a11-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="b7a11-144">Boolean.False</span></span>|  
|<span data-ttu-id="b7a11-145">"0"</span><span class="sxs-lookup"><span data-stu-id="b7a11-145">"0"</span></span>|<span data-ttu-id="b7a11-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="b7a11-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="b7a11-147">예를 들어, 다음과 같이 XML을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="b7a11-148">**입력**</span><span class="sxs-lookup"><span data-stu-id="b7a11-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>
```  
  
 <span data-ttu-id="b7a11-149">두 가지 모두 다음 코드에 의해 파악되며, **bvalue** 는 **System.Boolean.True** 입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True** :</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="b7a11-150">문자열을 Single 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="b7a11-150">String to Single</span></span>  
 <span data-ttu-id="b7a11-151">다음 표에서는 **ToSingle** 메서드를 사용하여 문자열을 **Single** 로 변환하는 경우 지정된 입력 문자열에 대해 생성되는 형식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="b7a11-152">유효한 문자열 입력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7a11-152">Valid string input parameter</span></span>|<span data-ttu-id="b7a11-153">.NET 출력 형식</span><span class="sxs-lookup"><span data-stu-id="b7a11-153">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="b7a11-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="b7a11-154">"INF"</span></span>|<span data-ttu-id="b7a11-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="b7a11-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="b7a11-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="b7a11-156">"-INF"</span></span>|<span data-ttu-id="b7a11-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="b7a11-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="b7a11-158">문자열을 Double 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="b7a11-158">String to Double</span></span>  
 <span data-ttu-id="b7a11-159">다음 표에서는 **ToDouble** 메서드를 사용하여 문자열을 **Single** 로 변환하는 경우 지정된 입력 문자열에 대해 생성되는 형식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="b7a11-160">유효한 문자열 입력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7a11-160">Valid string input parameter</span></span>|<span data-ttu-id="b7a11-161">.NET 출력 형식</span><span class="sxs-lookup"><span data-stu-id="b7a11-161">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="b7a11-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="b7a11-162">"INF"</span></span>|<span data-ttu-id="b7a11-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="b7a11-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="b7a11-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="b7a11-164">"-INF"</span></span>|<span data-ttu-id="b7a11-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="b7a11-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="b7a11-166">다음 코드는 `<Infinity>INF</Infinity>`를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a11-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7a11-167">참조</span><span class="sxs-lookup"><span data-stu-id="b7a11-167">See also</span></span>

- [<span data-ttu-id="b7a11-168">XML 데이터 형식 변환</span><span class="sxs-lookup"><span data-stu-id="b7a11-168">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)
- [<span data-ttu-id="b7a11-169">.NET 형식을 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="b7a11-169">Converting .NET Types to Strings</span></span>](converting-dotnet-types-to-strings.md)
