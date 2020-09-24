---
title: 날짜 및 시간 데이터
description: SQL Server에 대 한 .NET Framework Data Provider에서 날짜 및 시간 정보를 처리 하기 위한 데이터 형식에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: 6fe047fc672a2b42f886e81dcace91042a552932
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156318"
---
# <a name="date-and-time-data"></a><span data-ttu-id="fee2a-103">날짜 및 시간 데이터</span><span class="sxs-lookup"><span data-stu-id="fee2a-103">Date and Time Data</span></span>

<span data-ttu-id="fee2a-104">SQL Server 2008에는 날짜 및 시간 정보를 처리하기 위한 새로운 데이터 형식이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-104">SQL Server 2008 introduces new data types for handling date and time information.</span></span> <span data-ttu-id="fee2a-105">새 데이터 형식에는 날짜 및 시간에 대한 별도의 형식, 그리고 더 큰 범위, 전체 자릿수 및 표준 시간대 인식이 포함된 확장된 데이터 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-105">The new data types include separate types for date and time, and expanded data types with greater range, precision, and time-zone awareness.</span></span> <span data-ttu-id="fee2a-106">.NET Framework 버전 3.5 SP(서비스 팩) 1부터는 .NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient>)에 SQL Server 2008 데이터베이스 엔진의 새로운 모든 기능이 완벽하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-106">Starting with the .NET Framework version 3.5 Service Pack (SP) 1, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides full support for all the new features of the SQL Server 2008 Database Engine.</span></span> <span data-ttu-id="fee2a-107">SqlClient에서 이러한 새 기능을 사용하려면 .NET Framework 3.5 SP1 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-107">You must install the .NET Framework 3.5 SP1 (or later) to use these new features with SqlClient.</span></span>  
  
 <span data-ttu-id="fee2a-108">SQL Server 2008보다 이전의 SQL Server 버전에는 날짜 및 시간 값을 사용하기 위한 두 가지 데이터 형식 `datetime` 및 `smalldatetime`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-108">Versions of SQL Server earlier than SQL Server 2008 only had two data types for working with date and time values: `datetime` and `smalldatetime`.</span></span> <span data-ttu-id="fee2a-109">두 데이터 형식 모두 날짜 값과 시간 값을 모두 포함하므로 날짜나 시간 값만 가지고 작업하기는 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-109">Both of these data types contain both the date value and a time value, which makes it difficult to work with only date or only time values.</span></span> <span data-ttu-id="fee2a-110">또한 이러한 날짜 형식은 1753년 영국에 양력이 도입된 이후의 날짜만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-110">Also, these data types only support dates that occur after the introduction of the Gregorian calendar in England in 1753.</span></span> <span data-ttu-id="fee2a-111">또 다른 제한 사항은 이러한 이전 데이터 형식이 표준 시간대를 인식하지 못해 여러 표준 시간대에서 발생하는 데이터로 작업하기가 어렵다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-111">Another limitation is that these older data types are not time-zone aware, which makes it difficult to work with data that originates from multiple time zones.</span></span>  
  
 <span data-ttu-id="fee2a-112">SQL Server 온라인 설명서에서 SQL Server 데이터 형식에 대한 전체 설명을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-112">Complete documentation for SQL Server data types is available in SQL Server Books Online.</span></span> <span data-ttu-id="fee2a-113">다음 표에서는 날짜 및 시간 데이터에 대한 초급 수준의 항목을 버전별로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-113">The following table lists the version-specific entry-level topics for date and time data.</span></span>  
  
 <span data-ttu-id="fee2a-114">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="fee2a-114">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="fee2a-115">[날짜 및 시간 데이터 사용](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="fee2a-115">[Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a><span data-ttu-id="fee2a-116">SQL Server 2008에 도입된 날짜/시간 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fee2a-116">Date/Time Data Types Introduced in SQL Server 2008</span></span>  

 <span data-ttu-id="fee2a-117">다음 표에서는 새로운 날짜 및 시간 데이터 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-117">The following table describes the new date and time data types.</span></span>  
  
|<span data-ttu-id="fee2a-118">SQL Server 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fee2a-118">SQL Server data type</span></span>|<span data-ttu-id="fee2a-119">설명</span><span class="sxs-lookup"><span data-stu-id="fee2a-119">Description</span></span>|  
|--------------------------|-----------------|  
|`date`|<span data-ttu-id="fee2a-120">`date` 데이터 형식은 하루 단위이며 범위는 01년 1월 1일부터 9999년 12월 31일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-120">The `date` data type has a range of January 1, 01 through December 31, 9999 with an accuracy of 1 day.</span></span> <span data-ttu-id="fee2a-121">기본값은 1900년 1월 1일입니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-121">The default value is January 1, 1900.</span></span> <span data-ttu-id="fee2a-122">스토리지 크기는 3바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-122">The storage size is 3 bytes.</span></span>|  
|`time`|<span data-ttu-id="fee2a-123">`time` 데이터 형식은 24시간제를 기준으로 시간 값만 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-123">The `time` data type stores time values only, based on a 24-hour clock.</span></span> <span data-ttu-id="fee2a-124">`time` 데이터 형식의 범위는 00:00:00.0000000~23:59:59.9999999이며 정확도는 100나노초입니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-124">The `time` data type has a range of 00:00:00.0000000 through 23:59:59.9999999 with an accuracy of 100 nanoseconds.</span></span> <span data-ttu-id="fee2a-125">기본값은 00:00:00.0000000(자정)입니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-125">The default value is 00:00:00.0000000 (midnight).</span></span> <span data-ttu-id="fee2a-126">`time` 데이터 형식은 소수 자릿수 초 전체 자릿수에 대한 사용자 정의를 지원하며 저장 크기는 지정된 전체 자릿수에 따라 3~6바이트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-126">The `time` data type supports user-defined fractional second precision, and the storage size varies from 3 to 6 bytes, based on the precision specified.</span></span>|  
|`datetime2`|<span data-ttu-id="fee2a-127">`datetime2` 데이터 형식은 `date` 및 `time` 데이터 형식의 범위와 전체 자릿수를 단일 데이터 형식으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-127">The `datetime2` data type combines the range and precision of the `date` and `time` data types into a single data type.</span></span><br /><br /> <span data-ttu-id="fee2a-128">기본값과 문자열 리터럴 형식은 `date` 및 `time` 데이터 형식에 정의된 값과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-128">The default values and string literal formats are the same as those defined in the `date` and `time` data types.</span></span>|  
|`datetimeoffset`|<span data-ttu-id="fee2a-129">`datetimeoffset` 데이터 형식은 `datetime2`의 모든 기능을 포함하며 추가로 표준 시간대 오프셋 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-129">The `datetimeoffset` data type has all the features of `datetime2` with an additional time zone offset.</span></span> <span data-ttu-id="fee2a-130">표준 시간대 오프셋은 [+&#124;-] HH:MM으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-130">The time zone offset is represented as [+&#124;-] HH:MM.</span></span> <span data-ttu-id="fee2a-131">HH는 00에서 14 사이에 속하는 두 자리 숫자로, 표준 시간대 오프셋의 시간(시간)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-131">HH is 2 digits ranging from 00 to 14 that represent the number of hours in the time zone offset.</span></span> <span data-ttu-id="fee2a-132">MM은 00에서 59 사이에 속하는 두 자리 숫자로, 표준 시간대 오프셋의 추가 시간(분)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-132">MM is 2 digits ranging from 00 to 59 that represent the number of additional minutes in the time zone offset.</span></span> <span data-ttu-id="fee2a-133">이 시간 형식은 100나노초까지 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-133">Time formats are supported to 100 nanoseconds.</span></span> <span data-ttu-id="fee2a-134">필수 + 또는 - 부호는 현지 시간을 얻기 위해 표준 시간대 오프셋을 UTC(협정 세계시 또는 그리니치 표준시)에서 추가하거나 뺄 것인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-134">The mandatory + or - sign indicates whether the time zone offset is added or subtracted from UTC (Universal Time Coordinate or Greenwich Mean Time) to obtain the local time.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="fee2a-135">`Type System Version` 키워드 사용에 관한 자세한 내용은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fee2a-135">For more information about using the `Type System Version` keyword, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
## <a name="date-format-and-date-order"></a><span data-ttu-id="fee2a-136">날짜 형식 및 날짜 순서</span><span class="sxs-lookup"><span data-stu-id="fee2a-136">Date Format and Date Order</span></span>  

 <span data-ttu-id="fee2a-137">SQL Server가 날짜 및 시간 값을 구문 분석하는 방법은 형식 시스템 버전 및 서버 버전뿐만 아니라 서버의 기본 언어 및 형식 설정에 따라서도 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-137">How SQL Server parses date and time values depends not only on the type system version and server version, but also on the server's default language and format settings.</span></span> <span data-ttu-id="fee2a-138">다른 언어 및 날짜 형식 설정을 사용하는 연결에 의해 쿼리가 실행되는 경우 한 언어의 날짜 형식에 대해 작동하는 날짜 문자열이 인식되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-138">A date string that works for the date formats of one language might be unrecognizable if the query is executed by a connection that uses a different language and date format setting.</span></span>  
  
 <span data-ttu-id="fee2a-139">Transact-SQL SET LANGUAGE 문은 날짜 부분의 순서를 결정하는 DATEFORMAT를 묵시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-139">The Transact-SQL SET LANGUAGE statement implicitly sets the DATEFORMAT that determines the order of the date parts.</span></span> <span data-ttu-id="fee2a-140">연결에서 SET DATEFORMAT Transact-SQL 문을 사용하여 MDY, DMY, YMD, YDM, MYD 또는 DYM 순서의 날짜 부분을 정렬하여 날짜 값을 명확히 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-140">You can use the SET DATEFORMAT Transact-SQL statement on a connection to disambiguate date values by ordering the date parts in MDY, DMY, YMD, YDM, MYD, or DYM order.</span></span>  
  
 <span data-ttu-id="fee2a-141">연결에 대해 DATEFORMAT을 지정하지 않으면 SQL Server는 연결과 연결된 기본 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-141">If you do not specify any DATEFORMAT for the connection, SQL Server uses the default language associated with the connection.</span></span> <span data-ttu-id="fee2a-142">예를 들어 날짜 문자열 '01/02/03'은 언어 설정이 미국 영어인 서버에서는 MDY(2003년 1월 2일)로 해석되고 언어 설정이 영국 영어인 서버에서는 DMY(2003년 2월 1일)로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-142">For example, a date string of '01/02/03' would be interpreted as MDY (January 2, 2003) on a server with a language setting of United States English, and as DMY (February 1, 2003) on a server with a language setting of British English.</span></span> <span data-ttu-id="fee2a-143">연도는 세기 값을 할당하는 구분 날짜를 정의하는 SQL Server의 구분 연도 규칙을 사용하여 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-143">The year is determined by using SQL Server's cutoff year rule, which defines the cutoff date for assigning the century value.</span></span> <span data-ttu-id="fee2a-144">자세한 내용은 [두 자리 연도 구분 옵션](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fee2a-144">For more information, see [two digit year cutoff Option](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fee2a-145">문자열 형식에서 `date`, `time`, `datetime2` 또는 `datetimeoffset`로 변환할 때는 YDM 날짜 형식이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-145">The YDM date format is not supported when converting from a string format to `date`, `time`, `datetime2`, or `datetimeoffset`.</span></span>  
  
 <span data-ttu-id="fee2a-146">날짜 및 시간 데이터를 해석 SQL Server는 방법에 대 한 자세한 내용은 [날짜 및 시간 데이터 사용](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fee2a-146">For more information about how SQL Server interprets date and time data, see [Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).</span></span>  
  
## <a name="datetime-data-types-and-parameters"></a><span data-ttu-id="fee2a-147">날짜/시간 데이터 형식 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="fee2a-147">Date/Time Data Types and Parameters</span></span>  

 <span data-ttu-id="fee2a-148">새 날짜 및 시간 데이터 형식을 지원하기 위해 <xref:System.Data.SqlDbType>에 다음 열거형이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-148">The following enumerations have been added to <xref:System.Data.SqlDbType> to support the new date and time data types.</span></span>  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

<span data-ttu-id="fee2a-149">앞의 <xref:System.Data.SqlClient.SqlParameter> 열거형 중 하나를 사용하여 <xref:System.Data.SqlDbType>의 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-149">You can specify the data type of a <xref:System.Data.SqlClient.SqlParameter> by using one of the preceding <xref:System.Data.SqlDbType> enumerations.</span></span>

> [!NOTE]
> <span data-ttu-id="fee2a-150">`SqlParameter`의 `DbType` 속성을 `SqlDbType.Date`로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-150">You cannot set the `DbType` property of a `SqlParameter` to `SqlDbType.Date`.</span></span>

 <span data-ttu-id="fee2a-151">또한, `SqlParameter` 개체의 <xref:System.Data.SqlClient.SqlParameter.DbType%2A> 속성을 특정 <xref:System.Data.DbType> 열거형 값으로 설정하면 일반적인 방식으로 <xref:System.Data.SqlClient.SqlParameter>의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-151">You can also specify the type of a <xref:System.Data.SqlClient.SqlParameter> generically by setting the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> property of a `SqlParameter` object to a particular <xref:System.Data.DbType> enumeration value.</span></span> <span data-ttu-id="fee2a-152">`datetime2` 및 `datetimeoffset` 데이터 형식을 지원하기 위해 다음 열거형 값이 <xref:System.Data.DbType>에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-152">The following enumeration values have been added to <xref:System.Data.DbType> to support the `datetime2` and `datetimeoffset` data types:</span></span>  
  
- <span data-ttu-id="fee2a-153">DbType.DateTime2</span><span class="sxs-lookup"><span data-stu-id="fee2a-153">DbType.DateTime2</span></span>  
  
- <span data-ttu-id="fee2a-154">DbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fee2a-154">DbType.DateTimeOffset</span></span>  
  
 <span data-ttu-id="fee2a-155">이러한 새 열거형은 이전 버전의 .NET Framework에서 사용할 수 있는 `Date`, `Time` 및 `DateTime` 열거형을 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-155">These new enumerations supplement the `Date`, `Time`, and `DateTime` enumerations, which existed in earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="fee2a-156">매개 변수 개체의 .NET Framework 데이터 공급자 형식은 매개 변수 개체 값의 .NET Framework 형식이나 매개 변수 개체의 `DbType`에서 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-156">The .NET Framework data provider type of a parameter object is inferred from the .NET Framework type of the value of the parameter object, or from the `DbType` of the parameter object.</span></span> <span data-ttu-id="fee2a-157">새 날짜 및 시간 데이터 형식을 지원하기 위해 도입된 새로운 <xref:System.Data.SqlTypes> 데이터 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-157">No new <xref:System.Data.SqlTypes> data types have been introduced to support the new date and time data types.</span></span> <span data-ttu-id="fee2a-158">다음 표에서는 SQL Server 2008 날짜 및 시간 데이터 형식과 CLR 데이터 형식 간의 매핑에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-158">The following table describes the mappings between the SQL Server 2008 date and time data types and the CLR data types.</span></span>  
  
|<span data-ttu-id="fee2a-159">SQL Server 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fee2a-159">SQL Server data type</span></span>|<span data-ttu-id="fee2a-160">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="fee2a-160">.NET Framework type</span></span>|<span data-ttu-id="fee2a-161">System.Data.SqlDbType</span><span class="sxs-lookup"><span data-stu-id="fee2a-161">System.Data.SqlDbType</span></span>|<span data-ttu-id="fee2a-162">System.Data.DbType</span><span class="sxs-lookup"><span data-stu-id="fee2a-162">System.Data.DbType</span></span>|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|<span data-ttu-id="fee2a-163">date</span><span class="sxs-lookup"><span data-stu-id="fee2a-163">date</span></span>|<span data-ttu-id="fee2a-164">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-164">System.DateTime</span></span>|<span data-ttu-id="fee2a-165">날짜</span><span class="sxs-lookup"><span data-stu-id="fee2a-165">Date</span></span>|<span data-ttu-id="fee2a-166">날짜</span><span class="sxs-lookup"><span data-stu-id="fee2a-166">Date</span></span>|  
|<span data-ttu-id="fee2a-167">time</span><span class="sxs-lookup"><span data-stu-id="fee2a-167">time</span></span>|<span data-ttu-id="fee2a-168">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="fee2a-168">System.TimeSpan</span></span>|<span data-ttu-id="fee2a-169">Time</span><span class="sxs-lookup"><span data-stu-id="fee2a-169">Time</span></span>|<span data-ttu-id="fee2a-170">Time</span><span class="sxs-lookup"><span data-stu-id="fee2a-170">Time</span></span>|  
|<span data-ttu-id="fee2a-171">datetime2</span><span class="sxs-lookup"><span data-stu-id="fee2a-171">datetime2</span></span>|<span data-ttu-id="fee2a-172">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-172">System.DateTime</span></span>|<span data-ttu-id="fee2a-173">DateTime2</span><span class="sxs-lookup"><span data-stu-id="fee2a-173">DateTime2</span></span>|<span data-ttu-id="fee2a-174">DateTime2</span><span class="sxs-lookup"><span data-stu-id="fee2a-174">DateTime2</span></span>|  
|<span data-ttu-id="fee2a-175">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="fee2a-175">datetimeoffset</span></span>|<span data-ttu-id="fee2a-176">System.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fee2a-176">System.DateTimeOffset</span></span>|<span data-ttu-id="fee2a-177">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fee2a-177">DateTimeOffset</span></span>|<span data-ttu-id="fee2a-178">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fee2a-178">DateTimeOffset</span></span>|  
|<span data-ttu-id="fee2a-179">Datetime</span><span class="sxs-lookup"><span data-stu-id="fee2a-179">datetime</span></span>|<span data-ttu-id="fee2a-180">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-180">System.DateTime</span></span>|<span data-ttu-id="fee2a-181">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-181">DateTime</span></span>|<span data-ttu-id="fee2a-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-182">DateTime</span></span>|  
|<span data-ttu-id="fee2a-183">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="fee2a-183">smalldatetime</span></span>|<span data-ttu-id="fee2a-184">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-184">System.DateTime</span></span>|<span data-ttu-id="fee2a-185">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-185">DateTime</span></span>|<span data-ttu-id="fee2a-186">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-186">DateTime</span></span>|  
  
### <a name="sqlparameter-properties"></a><span data-ttu-id="fee2a-187">SqlParameter 속성</span><span class="sxs-lookup"><span data-stu-id="fee2a-187">SqlParameter Properties</span></span>  

 <span data-ttu-id="fee2a-188">다음 표에서는 날짜 및 시간 데이터 형식과 관련된 `SqlParameter` 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-188">The following table describes `SqlParameter` properties that are relevant to date and time data types.</span></span>  
  
|<span data-ttu-id="fee2a-189">속성</span><span class="sxs-lookup"><span data-stu-id="fee2a-189">Property</span></span>|<span data-ttu-id="fee2a-190">설명</span><span class="sxs-lookup"><span data-stu-id="fee2a-190">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|<span data-ttu-id="fee2a-191">값이 null을 허용하는지 여부를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-191">Gets or sets whether a value is nullable.</span></span> <span data-ttu-id="fee2a-192">Null 매개 변수 값을 서버에 보낼 때 `null`(Visual Basic에서는 `Nothing`) 대신 <xref:System.DBNull>을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-192">When you send a null parameter value to the server, you must specify <xref:System.DBNull>, rather than `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="fee2a-193">데이터베이스 null에 대 한 자세한 내용은 [Null 값 처리](handling-null-values.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fee2a-193">For more information about database nulls, see [Handling Null Values](handling-null-values.md).</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|<span data-ttu-id="fee2a-194">값을 나타내는 데 사용되는 최대 자릿수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-194">Gets or sets the maximum number of digits used to represent the value.</span></span> <span data-ttu-id="fee2a-195">날짜 및 시간 데이터 형식에 대해서는 이 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-195">This setting is ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|<span data-ttu-id="fee2a-196">`Time`, `DateTime2`, 및 `DateTimeOffset`의 날짜 부분 값이 확인되는 소수 자릿수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-196">Gets or sets the number of decimal places to which the time portion of the value is resolved for `Time`, `DateTime2`,and `DateTimeOffset`.</span></span> <span data-ttu-id="fee2a-197">기본값은 0이며,이 값은 실제 소수 자릿수가 값에서 유추되고 서버로 전송됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-197">The default value is 0, which means that the actual scale is inferred from the value and sent to the server.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="fee2a-198">날짜 및 시간 데이터 형식에 대해서는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-198">Ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="fee2a-199">매개 변수 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-199">Gets or sets the parameter value.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="fee2a-200">매개 변수 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-200">Gets or sets the parameter value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="fee2a-201">0보다 작거나 24시간보다 크거나 같은 시간 값은 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-201">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
### <a name="creating-parameters"></a><span data-ttu-id="fee2a-202">매개 변수 만들기</span><span class="sxs-lookup"><span data-stu-id="fee2a-202">Creating Parameters</span></span>  

 <span data-ttu-id="fee2a-203"><xref:System.Data.SqlClient.SqlParameter> 개체는 해당 생성자를 사용하거나, <xref:System.Data.SqlClient.SqlCommand>의 <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> 메서드를 호출하여 `Add`<xref:System.Data.SqlClient.SqlParameterCollection> 컬렉션에 추가하는 방법으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-203">You can create a <xref:System.Data.SqlClient.SqlParameter> object by using its constructor, or by adding it to a <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection by calling the `Add` method of the <xref:System.Data.SqlClient.SqlParameterCollection>.</span></span> <span data-ttu-id="fee2a-204">`Add` 메서드는 생성자 인수 또는 기존 매개 변수 개체를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-204">The `Add` method will take as input either constructor arguments or an existing parameter object.</span></span>  
  
 <span data-ttu-id="fee2a-205">이 항목의 다음 섹션에서는 날짜 및 시간 매개 변수를 지정하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-205">The next sections in this topic provide examples of how to specify date and time parameters.</span></span> <span data-ttu-id="fee2a-206">매개 변수 사용에 대 한 추가 예제는 [매개 변수 및 매개 변수 데이터 형식](../configuring-parameters-and-parameter-data-types.md) 및 [DataAdapter 매개 변수](../dataadapter-parameters.md)구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fee2a-206">For additional examples of working with parameters, see [Configuring Parameters and Parameter Data Types](../configuring-parameters-and-parameter-data-types.md) and [DataAdapter Parameters](../dataadapter-parameters.md).</span></span>  
  
### <a name="date-example"></a><span data-ttu-id="fee2a-207">Date 예제</span><span class="sxs-lookup"><span data-stu-id="fee2a-207">Date Example</span></span>  

 <span data-ttu-id="fee2a-208">다음 코드 조각에서는 `date` 매개 변수를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-208">The following code fragment demonstrates how to specify a `date` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### <a name="time-example"></a><span data-ttu-id="fee2a-209">Time 예제</span><span class="sxs-lookup"><span data-stu-id="fee2a-209">Time Example</span></span>  

 <span data-ttu-id="fee2a-210">다음 코드 조각에서는 `time` 매개 변수를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-210">The following code fragment demonstrates how to specify a `time` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### <a name="datetime2-example"></a><span data-ttu-id="fee2a-211">Datetime2 예제</span><span class="sxs-lookup"><span data-stu-id="fee2a-211">Datetime2 Example</span></span>  

 <span data-ttu-id="fee2a-212">다음 코드 조각에서는 날짜 및 시간 부분을 모두 사용하여 `datetime2` 매개 변수를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-212">The following code fragment demonstrates how to specify a `datetime2` parameter with both the date and time parts.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### <a name="datetimeoffset-example"></a><span data-ttu-id="fee2a-213">DateTimeOffSet 예제</span><span class="sxs-lookup"><span data-stu-id="fee2a-213">DateTimeOffSet Example</span></span>  

 <span data-ttu-id="fee2a-214">다음 코드 조각에서는 날짜, 시간 및 표준 시간대 오프셋이 0인 `DateTimeOffSet` 매개 변수를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-214">The following code fragment demonstrates how to specify a `DateTimeOffSet` parameter with a date, a time, and a time zone offset of 0.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### <a name="addwithvalue"></a><span data-ttu-id="fee2a-215">AddWithValue</span><span class="sxs-lookup"><span data-stu-id="fee2a-215">AddWithValue</span></span>  

 <span data-ttu-id="fee2a-216">다음 코드 조각과 같이 <xref:System.Data.SqlClient.SqlCommand>의 `AddWithValue` 메서드를 사용하여 매개 변수를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-216">You can also supply parameters by using the `AddWithValue` method of a <xref:System.Data.SqlClient.SqlCommand>, as shown in the following code fragment.</span></span> <span data-ttu-id="fee2a-217">그러나 `AddWithValue` 메서드에서는 매개 변수에 <xref:System.Data.SqlClient.SqlParameter.DbType%2A> 또는 <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-217">However, the `AddWithValue` method does not allow you to specify the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> or <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> for the parameter.</span></span>  
  
```csharp  
command.Parameters.AddWithValue(
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 <span data-ttu-id="fee2a-218">`@date` 매개 변수는 서버의 `date`, `datetime` 또는 `datetime2` 데이터 형식에 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-218">The `@date` parameter could map to a `date`, `datetime`, or `datetime2` data type on the server.</span></span> <span data-ttu-id="fee2a-219">새 `datetime` 데이터 형식으로 작업하는 경우 매개 변수의 <xref:System.Data.SqlDbType> 속성을 명시적으로 인스턴스의 데이터 형식으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-219">When working with the new `datetime` data types, you must explicitly set the parameter's <xref:System.Data.SqlDbType> property to the data type of the instance.</span></span> <span data-ttu-id="fee2a-220"><xref:System.Data.SqlDbType.Variant>를 사용하거나 매개 변수 값을 암시적으로 제공하면 `datetime` 및 `smalldatetime` 데이터 형식에 이전 버전 호환성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-220">Using <xref:System.Data.SqlDbType.Variant> or implicitly supplying parameter values can cause problems with backward compatibility with the `datetime` and `smalldatetime` data types.</span></span>  
  
 <span data-ttu-id="fee2a-221">다음 표에서는 CLR 형식에서 유추되는 `SqlDbTypes`를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-221">The following table shows which `SqlDbTypes` are inferred from which CLR types:</span></span>  
  
|<span data-ttu-id="fee2a-222">CLR 형식</span><span class="sxs-lookup"><span data-stu-id="fee2a-222">CLR type</span></span>|<span data-ttu-id="fee2a-223">유추된 SqlDbType</span><span class="sxs-lookup"><span data-stu-id="fee2a-223">Inferred SqlDbType</span></span>|  
|--------------|------------------------|  
|<span data-ttu-id="fee2a-224">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-224">DateTime</span></span>|<span data-ttu-id="fee2a-225">SqlDbType.DateTime</span><span class="sxs-lookup"><span data-stu-id="fee2a-225">SqlDbType.DateTime</span></span>|  
|<span data-ttu-id="fee2a-226">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="fee2a-226">TimeSpan</span></span>|<span data-ttu-id="fee2a-227">SqlDbType.Time</span><span class="sxs-lookup"><span data-stu-id="fee2a-227">SqlDbType.Time</span></span>|  
|<span data-ttu-id="fee2a-228">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fee2a-228">DateTimeOffset</span></span>|<span data-ttu-id="fee2a-229">SqlDbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fee2a-229">SqlDbType.DateTimeOffset</span></span>|  
  
## <a name="retrieving-date-and-time-data"></a><span data-ttu-id="fee2a-230">날짜 및 시간 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="fee2a-230">Retrieving Date and Time Data</span></span>  

 <span data-ttu-id="fee2a-231">다음 표에서는 SQL Server 2008 날짜 및 시간 값을 검색하는 데 사용되는 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-231">The following table describes methods that are used to retrieve SQL Server 2008 date and time values.</span></span>  
  
|<span data-ttu-id="fee2a-232">SqlClient 메서드</span><span class="sxs-lookup"><span data-stu-id="fee2a-232">SqlClient method</span></span>|<span data-ttu-id="fee2a-233">설명</span><span class="sxs-lookup"><span data-stu-id="fee2a-233">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|<span data-ttu-id="fee2a-234">지정된 열 값을 <xref:System.DateTime> 구조체로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-234">Retrieves the specified column value as a <xref:System.DateTime> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|<span data-ttu-id="fee2a-235">지정된 열 값을 <xref:System.DateTimeOffset> 구조체로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-235">Retrieves the specified column value as a <xref:System.DateTimeOffset> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|<span data-ttu-id="fee2a-236">필드에 대해 기본 공급자별 형식인 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-236">Returns the type that is the underlying provider-specific type for the field.</span></span> <span data-ttu-id="fee2a-237">새 날짜 및 시간 형식에 대해 `GetFieldType`과 동일한 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-237">Returns the same types as `GetFieldType` for new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|<span data-ttu-id="fee2a-238">지정한 열의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-238">Retrieves the value of the specified column.</span></span> <span data-ttu-id="fee2a-239">새 날짜 및 시간 형식에 대해 `GetValue`와 동일한 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-239">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|<span data-ttu-id="fee2a-240">지정된 배열의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-240">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<span data-ttu-id="fee2a-241">열 값을 <xref:System.Data.SqlTypes.SqlString>으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-241">Retrieves the column value as a <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="fee2a-242">데이터를 `SqlString`으로 표현할 수 없는 경우 <xref:System.InvalidCastException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-242">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a `SqlString`.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|<span data-ttu-id="fee2a-243">열 데이터를 기본 `SqlDbType`으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-243">Retrieves column data as its default `SqlDbType`.</span></span> <span data-ttu-id="fee2a-244">새 날짜 및 시간 형식에 대해 `GetValue`와 동일한 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-244">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|<span data-ttu-id="fee2a-245">지정된 배열의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-245">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|<span data-ttu-id="fee2a-246">Type System Version이 SQL Server 2005로 설정되어 있는 경우 열 값을 문자열로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-246">Retrieves the column value as a string if the Type System Version is set to SQL Server 2005.</span></span> <span data-ttu-id="fee2a-247">데이터를 문자열로 표현할 수 없는 경우 <xref:System.InvalidCastException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-247">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a string.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|<span data-ttu-id="fee2a-248">지정된 열 값을 <xref:System.TimeSpan> 구조체로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-248">Retrieves the specified column value as a <xref:System.TimeSpan> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|<span data-ttu-id="fee2a-249">지정된 열 값을 기본 CLR 형식으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-249">Retrieves the specified column value as its underlying CLR type.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|<span data-ttu-id="fee2a-250">배열에서 열 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-250">Retrieves column values in an array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|<span data-ttu-id="fee2a-251">결과 집합의 메타데이터를 설명하는 <xref:System.Data.DataTable>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-251">Returns a <xref:System.Data.DataTable> that describes the metadata of the result set.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="fee2a-252">SQL Server에서 in-process로 실행되는 코드에는 새로운 날짜 및 시간 `SqlDbTypes`이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-252">The new date and time `SqlDbTypes` are not supported for code that is executing in-process in SQL Server.</span></span> <span data-ttu-id="fee2a-253">이러한 형식 중 하나가 서버에 전달되면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-253">An exception will be raised if one of these types is passed to the server.</span></span>  
  
## <a name="specifying-date-and-time-values-as-literals"></a><span data-ttu-id="fee2a-254">날짜 및 시간 값을 리터럴로 지정</span><span class="sxs-lookup"><span data-stu-id="fee2a-254">Specifying Date and Time Values as Literals</span></span>  

 <span data-ttu-id="fee2a-255">날짜 및 시간 데이터 형식은 다양한 리터럴 문자열 형식을 사용하여 지정할 수 있으며, 그러면 SQL Server가 런타임에 해당 형식을 평가하여 내부 날짜/시간 구조체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-255">You can specify date and time data types by using a variety of different literal string formats, which SQL Server then evaluates at run time, converting them to internal date/time structures.</span></span> <span data-ttu-id="fee2a-256">SQL Server는 작은따옴표(')로 묶인 날짜 및 시간 데이터를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-256">SQL Server recognizes date and time data that is enclosed in single quotation marks (').</span></span> <span data-ttu-id="fee2a-257">다음은 일부 형식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-257">The following examples demonstrate some formats:</span></span>  
  
- <span data-ttu-id="fee2a-258">`'October 15, 2006'`과 같은 영문자 날짜 형식.</span><span class="sxs-lookup"><span data-stu-id="fee2a-258">Alphabetic date formats, such as `'October 15, 2006'`.</span></span>  
  
- <span data-ttu-id="fee2a-259">`'10/15/2006'`과 같은 숫자 날짜 형식.</span><span class="sxs-lookup"><span data-stu-id="fee2a-259">Numeric date formats, such as `'10/15/2006'`.</span></span>  
  
- <span data-ttu-id="fee2a-260">`'20061015'`와 같은 구분되지 않은 문자열 형식(ISO 표준 날짜 형식을 사용하는 경우 2006년 10월 15일로 해석됨).</span><span class="sxs-lookup"><span data-stu-id="fee2a-260">Unseparated string formats, such as `'20061015'`, which would be interpreted as October 15, 2006 if you are using the ISO standard date format.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fee2a-261">SQL Server 온라인 설명서에서 날짜 및 시간 데이터 형식의 모든 리터럴 문자열 형식 및 기타 기능에 대한 전체 설명을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-261">You can find complete documentation for all of the literal string formats and other features of the date and time data types in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="fee2a-262">0보다 작거나 24시간보다 크거나 같은 시간 값은 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-262">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="fee2a-263">SQL Server 온라인 설명서 내 리소스</span><span class="sxs-lookup"><span data-stu-id="fee2a-263">Resources in SQL Server Books Online</span></span>  

 <span data-ttu-id="fee2a-264">SQL Server에서 날짜 및 시간 값을 사용 하는 방법에 대 한 자세한 내용은 SQL Server 온라인 설명서에서 다음 리소스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fee2a-264">For more information about working with date and time values in SQL Server, see the following resources in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="fee2a-265">항목</span><span class="sxs-lookup"><span data-stu-id="fee2a-265">Topic</span></span>|<span data-ttu-id="fee2a-266">설명</span><span class="sxs-lookup"><span data-stu-id="fee2a-266">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fee2a-267">날짜 및 시간 데이터 형식 및 함수(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fee2a-267">Date and Time Data Types and Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|<span data-ttu-id="fee2a-268">모든 Transact-SQL 날짜 및 시간 데이터 형식 및 함수에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-268">Provides an overview of all Transact-SQL date and time data types and functions.</span></span>|  
|<span data-ttu-id="fee2a-269">[날짜 및 시간 데이터 사용](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="fee2a-269">[Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>|<span data-ttu-id="fee2a-270">날짜 및 시간 데이터 형식 및 함수에 관한 정보와 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-270">Provides information about the date and time data types and functions, and examples of using them.</span></span>|  
|[<span data-ttu-id="fee2a-271">데이터 형식(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fee2a-271">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)|<span data-ttu-id="fee2a-272">SQL Server의 시스템 데이터 형식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee2a-272">Describes system data types in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fee2a-273">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fee2a-273">See also</span></span>

- [<span data-ttu-id="fee2a-274">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="fee2a-274">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="fee2a-275">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="fee2a-275">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="fee2a-276">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fee2a-276">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="fee2a-277">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="fee2a-277">ADO.NET Overview</span></span>](../ado-net-overview.md)
