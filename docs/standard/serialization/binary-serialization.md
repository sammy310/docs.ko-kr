---
title: 이진 Serialization
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 9df9b73a1a1347b952d76b76c9058578f5e9f401
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401270"
---
# <a name="binary-serialization"></a><span data-ttu-id="c1c72-102">이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="c1c72-102">Binary serialization</span></span>

<span data-ttu-id="c1c72-103">serialization은 개체의 상태를 스토리지 매체에 스토리지하는 프로세스로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="c1c72-104">이 프로세스 도중 클래스가 포함된 어셈블리를 포함하여 개체의 public 및 private 필드와 클래스의 이름을 바이트의 스트림으로 변환한 다음 데이터 스트림에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="c1c72-105">그런 다음 개체가 역직렬화되면 원본 개체의 정확한 복제본이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="c1c72-106">개체 지향적 환경에서 serialization 메커니즘을 구현할 때는 사용 편의성과 유연성 사이에서 균형을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="c1c72-107">프로세스를 충분히 제어할 수 있으면 프로세스의 많은 부분을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="c1c72-108">예를 들어 단순한 이진 serialization로 충분하지 않거나 클래스의 필드를 serialize해야 하는 것으로 결정할 특별한 이유가 있는 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="c1c72-109">다음 섹션에서는 .NET에서 제공하는 강력한 serialization 메커니즘을 살펴보고 프로세스를 필요에 따라 사용자 지정할 수 있는 몇 가지 중요한 기능을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="c1c72-110">UTF-8 또는 UTF-7로 인코딩된 개체가 서로 다른 .NET Framework 버전을 사용하여 직렬화되고 역직렬화될 경우 해당 개체의 상태는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="c1c72-111">이진 직렬화를 사용하면 개체 내부의 개인 멤버를 수정하여 상태를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-111">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="c1c72-112">따라서 public API 표면에서 작동하는 <xref:System.Text.Json?displayProperty=fullName>와 같은 다른 직렬화 프레임워크를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-112">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="c1c72-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="c1c72-113">.NET Core</span></span>

<span data-ttu-id="c1c72-114">.NET Core는 형식의 하위 집합에 대해 이진 직렬화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-114">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="c1c72-115">다음 의 [Serializable 형식](#serializable-types) 섹션에서 지원되는 형식 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-115">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="c1c72-116">나열된 형식은 .NET Framework 4.5.1 이후 버전과 .NET Core 2.0 및 이후 버전 간에 직렬화할 수 있음을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-116">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="c1c72-117">Mono와 같은 다른 .NET 구현은 공식적으로 지원되지 않지만 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-117">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="c1c72-118">직렬화 가능 형식</span><span class="sxs-lookup"><span data-stu-id="c1c72-118">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="c1c72-119">Type</span><span class="sxs-lookup"><span data-stu-id="c1c72-119">Type</span></span> | <span data-ttu-id="c1c72-120">메모</span><span class="sxs-lookup"><span data-stu-id="c1c72-120">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-121">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-121">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-122">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-122">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-123">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-124">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-125">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-126">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-127">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-128">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-129">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-130">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-131">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-132">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-133">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-134">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="c1c72-135">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-136">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-137">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-138">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-139">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-140">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-140">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="c1c72-141">.NET 프레임워크에서 .NET 코어로 의 직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-141">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-142">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-142">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="c1c72-143">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-143">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-144">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-145">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-146">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-147">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-148">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-149">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-150">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="c1c72-151">.NET 코어 2.0.2 이후 버전부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-151">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-152">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-153">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-153">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-154">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-155">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="c1c72-156">`SerializationFormat.Binary`을 설정하면 `RemotingFormat` .NET Core 2.1 및 이후 버전에서만 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-156">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-157">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-158">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-158">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-159">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-160">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-161">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-162">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-163">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-164">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-165">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-166">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-167">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-168">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-169">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-169">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="c1c72-170">.NET 프레임워크에서 .NET 코어로 의 직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-170">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-171">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-171">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-172">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-172">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-173">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-174">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-175">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-176">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-177">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-178">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-179">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="c1c72-180">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-181">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-182">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-183">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-184">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-185">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-186">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-187">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-188">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-189">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-190">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-191">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-192">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-193">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-194">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-195">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-196">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-197">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-198">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-199">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-200">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-201">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-202">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-203">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-204">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-205">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="c1c72-206">.NET 코어 2.0.6부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-206">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-207">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-208">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-208">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-209">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-210">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="c1c72-211">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-212">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-213">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-214">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-215">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-216">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-217">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-218">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-219">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-220">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-221">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-222">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-223">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-224">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-225">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-226">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-227">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-228">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-229">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-230">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-231">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-232">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-233">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-234">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-235">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-236">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-237">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-238">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-239">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-240">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-241">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-242">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-243">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-244">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-245">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-246">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-247">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-248">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-249">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-250">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-251">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-252">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-253">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-254">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-255">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-256">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-257">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-258">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-259">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-259">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="c1c72-260">.NET 프레임워크에서 .NET 코어로 의 직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-260">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-261">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-261">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-262">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-262">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-263">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-264">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-265">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-266">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-267">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-268">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-269">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-270">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-271">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-272">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-273">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-274">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-275">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-276">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-277">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-278">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-279">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-280">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-281">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-281">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="c1c72-282">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-283">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-283">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-284">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-285">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-286">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-286">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="c1c72-287">제한된 직렬화 데이터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-287">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-288">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-288">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-289">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-289">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-290">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-291">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-292">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-293">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-294">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-295">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-296">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-297">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-298">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-299">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-300">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-301">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-302">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-303">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-304">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-305">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-306">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-307">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-308">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-309">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-310">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-311">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-312">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-313">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-314">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-315">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-316">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-317">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-318">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-319">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-320">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="c1c72-321">.NET Framework 4.7 및 이전 버전에서는 직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-321">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-322">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-323">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-323">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-324">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-325">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-326">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-327">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="c1c72-328">.NET 코어 2.0.4부터.</span><span class="sxs-lookup"><span data-stu-id="c1c72-328">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c1c72-329">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1c72-329">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="c1c72-330">개체를 직렬화하거나 역직렬화하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-330">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="c1c72-331">[XML 및 비누 직렬화](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="c1c72-331">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="c1c72-332">공용 언어 런타임에 포함된 XML serialization 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-332">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="c1c72-333">[보안 및 직렬화](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="c1c72-333">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="c1c72-334">serialization을 수행하는 코드를 쓸 때 따를 보안 코딩 지침을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-334">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="c1c72-335">[.NET 리모팅](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c1c72-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="c1c72-336">원격 통신을 위해 .NET Framework에서 시작하는 다양한 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-336">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="c1c72-337">[ASP.NET 및 XML 웹 서비스 클라이언트를 사용하여 만든 XML 웹 서비스](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c1c72-337">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="c1c72-338">ASP.NET 사용하여 만든 XML 웹 서비스를 프로그래밍하는 방법을 설명하고 설명하는 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c72-338">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
