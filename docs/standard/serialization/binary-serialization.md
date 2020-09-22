---
title: 이진 Serialization
description: 이 문서에서는 .NET Core에서 지원하는 이진 serialization 및 형식을 설명합니다. 이진 serialization의 위험성과 그 대안을 알아야 합니다.
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
ms.openlocfilehash: 2ede74dd8a48735a7ded450d1da6d9cda8fc5ae6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554497"
---
# <a name="binary-serialization"></a><span data-ttu-id="07cff-104">이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="07cff-104">Binary serialization</span></span>

<span data-ttu-id="07cff-105">serialization은 개체의 상태를 스토리지 매체에 스토리지하는 프로세스로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-105">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="07cff-106">이 프로세스 도중 클래스가 포함된 어셈블리를 포함하여 개체의 public 및 private 필드와 클래스의 이름을 바이트의 스트림으로 변환한 다음 데이터 스트림에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-106">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="07cff-107">그런 다음 개체가 역직렬화되면 원본 개체의 정확한 복제본이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-107">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="07cff-108">개체 지향적 환경에서 serialization 메커니즘을 구현할 때는 사용 편의성과 유연성 사이에서 균형을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-108">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="07cff-109">프로세스를 충분히 제어할 수 있으면 프로세스의 많은 부분을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-109">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="07cff-110">예를 들어 단순한 이진 serialization로 충분하지 않거나 클래스의 필드를 serialize해야 하는 것으로 결정할 특별한 이유가 있는 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-110">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="07cff-111">다음 섹션에서는 .NET에서 제공하는 강력한 serialization 메커니즘을 살펴보고 프로세스를 필요에 따라 사용자 지정할 수 있는 몇 가지 중요한 기능을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-111">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="07cff-112">UTF-8 또는 UTF-7로 인코딩된 개체가 서로 다른 .NET Framework 버전을 사용하여 직렬화되고 역직렬화될 경우 해당 개체의 상태는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-112">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="07cff-113">이진 serialization을 사용하면 개체 내에서 전용 멤버를 수정할 수 있으며, 따라서 개체의 상태를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-113">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="07cff-114">이 때문에 공용 API 노출 영역에서 작동하는 다른 serialization 프레임워크(예: <xref:System.Text.Json?displayProperty=fullName>)가 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-114">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="07cff-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="07cff-115">.NET Core</span></span>

<span data-ttu-id="07cff-116">.NET Core는 형식의 하위 집합에 대한 이진 serialization을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-116">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="07cff-117">지원되는 형식 목록은 이어지는 [직렬화 가능 형식](#serializable-types) 섹션에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-117">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="07cff-118">나열된 형식은 .NET Framework 4.5.1 이상 버전 및 .NET Core 2.0 이상 버전 간에 직렬화 가능 형식으로 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-118">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="07cff-119">Mono 같은 다른 .NET 구현은 공식적으로 지원되지 않지만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-119">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="07cff-120">직렬화 가능 형식</span><span class="sxs-lookup"><span data-stu-id="07cff-120">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="07cff-121">형식</span><span class="sxs-lookup"><span data-stu-id="07cff-121">Type</span></span> | <span data-ttu-id="07cff-122">참고</span><span class="sxs-lookup"><span data-stu-id="07cff-122">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="07cff-123">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="07cff-124">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-125">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="07cff-126">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-127">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-128">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="07cff-129">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="07cff-130">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="07cff-131">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="07cff-132">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="07cff-133">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="07cff-134">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="07cff-135">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-136">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-136">Starting in .NET Core 2.0.4.</span></span> |
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
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="07cff-137">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-138">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="07cff-139">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="07cff-140">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-140">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="07cff-141">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-141">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="07cff-142">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-142">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="07cff-143">.NET Framework에서 .NET Core로의 serialization은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-143">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="07cff-144">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="07cff-145">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="07cff-146">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-147">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="07cff-148">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="07cff-149">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-150">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="07cff-151">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-151">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="07cff-152">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="07cff-153">.NET Core 2.0.2 이상 버전에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-153">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="07cff-154">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="07cff-155">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="07cff-156">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-156">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="07cff-157">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="07cff-158">`RemotingFormat`을 `SerializationFormat.Binary`로 설정하면 .NET Core 2.1 이상 버전과만 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-158">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="07cff-159">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="07cff-160">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="07cff-161">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="07cff-162">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="07cff-163">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="07cff-164">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="07cff-165">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-166">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="07cff-167">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-168">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="07cff-169">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-169">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="07cff-170">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-170">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="07cff-171">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-171">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="07cff-172">.NET Framework에서 .NET Core로의 serialization은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-172">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="07cff-173">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="07cff-174">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="07cff-175">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="07cff-176">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="07cff-177">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="07cff-178">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="07cff-179">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-180">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-181">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="07cff-182">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="07cff-183">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-184">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="07cff-185">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="07cff-186">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="07cff-187">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="07cff-188">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="07cff-189">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-190">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="07cff-191">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="07cff-192">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-193">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-194">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="07cff-195">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="07cff-196">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-197">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="07cff-198">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="07cff-199">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="07cff-200">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-201">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="07cff-202">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-203">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="07cff-204">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-205">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="07cff-206">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-206">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-207">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="07cff-208">.NET Core 2.0.6에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-208">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="07cff-209">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="07cff-210">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="07cff-211">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-212">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="07cff-213">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-214">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="07cff-215">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="07cff-216">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="07cff-217">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-218">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="07cff-219">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="07cff-220">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="07cff-221">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="07cff-222">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="07cff-223">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="07cff-224">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="07cff-225">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="07cff-226">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="07cff-227">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-228">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="07cff-229">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="07cff-230">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="07cff-231">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="07cff-232">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="07cff-233">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="07cff-234">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="07cff-235">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-236">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="07cff-237">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="07cff-238">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="07cff-239">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="07cff-240">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="07cff-241">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-242">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="07cff-243">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-244">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="07cff-245">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="07cff-246">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="07cff-247">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="07cff-248">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-249">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-250">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="07cff-251">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-252">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="07cff-253">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="07cff-254">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="07cff-255">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-256">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="07cff-257">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="07cff-258">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="07cff-259">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-259">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="07cff-260">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-260">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="07cff-261">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-261">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="07cff-262">.NET Framework에서 .NET Core로의 serialization은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-262">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="07cff-263">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-264">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="07cff-265">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="07cff-266">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="07cff-267">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-268">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="07cff-269">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="07cff-270">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="07cff-271">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="07cff-272">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="07cff-273">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="07cff-274">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="07cff-275">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="07cff-276">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="07cff-277">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-278">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="07cff-279">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-280">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="07cff-281">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-281">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="07cff-282">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-283">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-283">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="07cff-284">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="07cff-285">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="07cff-286">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-286">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-287">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-287">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="07cff-288">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-288">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="07cff-289">제한된 serialization 데이터.</span><span class="sxs-lookup"><span data-stu-id="07cff-289">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-290">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="07cff-291">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="07cff-292">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="07cff-293">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="07cff-294">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="07cff-295">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="07cff-296">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="07cff-297">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="07cff-298">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="07cff-299">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="07cff-300">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="07cff-301">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="07cff-302">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="07cff-303">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="07cff-304">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="07cff-305">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-306">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="07cff-307">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="07cff-308">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-309">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="07cff-310">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="07cff-311">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-312">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="07cff-313">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="07cff-314">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-315">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="07cff-316">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="07cff-317">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-318">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="07cff-319">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="07cff-320">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="07cff-321">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-321">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="07cff-322">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="07cff-323">.NET Framework 4.7 및 이전 버전에서는 직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-323">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="07cff-324">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="07cff-325">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="07cff-326">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="07cff-327">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="07cff-328">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-328">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="07cff-329">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-329">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="07cff-330">.NET Core 2.0.4에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-330">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="07cff-331">참조</span><span class="sxs-lookup"><span data-stu-id="07cff-331">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="07cff-332">개체를 직렬화하거나 역직렬화하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-332">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="07cff-333">[XML 및 SOAP Serialization](xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="07cff-333">[XML and SOAP Serialization](xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="07cff-334">공용 언어 런타임에 포함된 XML serialization 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-334">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="07cff-335">[보안 및 Serialization](../../framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="07cff-335">[Security and Serialization](../../framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="07cff-336">serialization을 수행하는 코드를 쓸 때 따를 보안 코딩 지침을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-336">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="07cff-337">[.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="07cff-337">[.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="07cff-338">원격 통신을 위해 .NET Framework에서 시작하는 다양한 메서드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-338">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="07cff-339">[ASP.NET 및 XML Web Service 클라이언트를 사용하여 만든 XML Web Services](/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="07cff-339">[XML Web Services Created Using ASP.NET and XML Web Service Clients](/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="07cff-340">ASP.NET을 사용하여 만든 XML Web services를 프로그래밍하는 방법을 설명하는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="07cff-340">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
