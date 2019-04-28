---
title: ODBC 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772049"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="9a0d4-102">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="9a0d4-102">ODBC Schema Collections</span></span>

<span data-ttu-id="9a0d4-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="9a0d4-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="9a0d4-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="9a0d4-105">Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="9a0d4-106">Tables</span><span class="sxs-lookup"><span data-stu-id="9a0d4-106">Tables</span></span>

- <span data-ttu-id="9a0d4-107">인덱스</span><span class="sxs-lookup"><span data-stu-id="9a0d4-107">Indexes</span></span>

- <span data-ttu-id="9a0d4-108">Columns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-108">Columns</span></span>

- <span data-ttu-id="9a0d4-109">절차</span><span class="sxs-lookup"><span data-stu-id="9a0d4-109">Procedures</span></span>

- <span data-ttu-id="9a0d4-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-110">ProcedureColumns</span></span>

- <span data-ttu-id="9a0d4-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9a0d4-111">ProcedureParameters</span></span>

- <span data-ttu-id="9a0d4-112">보기</span><span class="sxs-lookup"><span data-stu-id="9a0d4-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="9a0d4-113">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="9a0d4-113">Tables and Views</span></span>

|<span data-ttu-id="9a0d4-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-114">ColumnName</span></span>|<span data-ttu-id="9a0d4-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9a0d4-116">TABLE_CAT</span></span>|<span data-ttu-id="9a0d4-117">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-117">String</span></span>|
|<span data-ttu-id="9a0d4-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9a0d4-118">TABLE_SCHEM</span></span>|<span data-ttu-id="9a0d4-119">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-119">String</span></span>|
|<span data-ttu-id="9a0d4-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-120">TABLE_NAME</span></span>|<span data-ttu-id="9a0d4-121">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-121">String</span></span>|
|<span data-ttu-id="9a0d4-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-122">TABLE_TYPE</span></span>|<span data-ttu-id="9a0d4-123">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-123">String</span></span>|
|<span data-ttu-id="9a0d4-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-124">REMARKS</span></span>|<span data-ttu-id="9a0d4-125">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="9a0d4-126">인덱스</span><span class="sxs-lookup"><span data-stu-id="9a0d4-126">Indexes</span></span>

|<span data-ttu-id="9a0d4-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-127">ColumnName</span></span>|<span data-ttu-id="9a0d4-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9a0d4-129">TABLE_CAT</span></span>|<span data-ttu-id="9a0d4-130">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-130">String</span></span>|
|<span data-ttu-id="9a0d4-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9a0d4-131">TABLE_SCHEM</span></span>|<span data-ttu-id="9a0d4-132">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-132">String</span></span>|
|<span data-ttu-id="9a0d4-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-133">TABLE_NAME</span></span>|<span data-ttu-id="9a0d4-134">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-134">String</span></span>|
|<span data-ttu-id="9a0d4-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-135">NON_UNIQUE</span></span>|<span data-ttu-id="9a0d4-136">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-136">Int16</span></span>|
|<span data-ttu-id="9a0d4-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-138">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-138">String</span></span>|
|<span data-ttu-id="9a0d4-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-139">INDEX_NAME</span></span>|<span data-ttu-id="9a0d4-140">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-140">String</span></span>|
|<span data-ttu-id="9a0d4-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-141">TYPE</span></span>|<span data-ttu-id="9a0d4-142">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-142">Int16</span></span>|
|<span data-ttu-id="9a0d4-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-144">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-144">Int16</span></span>|
|<span data-ttu-id="9a0d4-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-145">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-146">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-146">String</span></span>|
|<span data-ttu-id="9a0d4-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="9a0d4-147">ASC_OR_DESC</span></span>|<span data-ttu-id="9a0d4-148">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-148">String</span></span>|
|<span data-ttu-id="9a0d4-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9a0d4-149">CARDINALITY</span></span>|<span data-ttu-id="9a0d4-150">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-150">Int32</span></span>|
|<span data-ttu-id="9a0d4-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="9a0d4-151">PAGES</span></span>|<span data-ttu-id="9a0d4-152">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-152">Int32</span></span>|
|<span data-ttu-id="9a0d4-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-153">FILTER_CONDITION</span></span>|<span data-ttu-id="9a0d4-154">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-154">String</span></span>|
|<span data-ttu-id="9a0d4-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a0d4-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9a0d4-156">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-156">String</span></span>|
|<span data-ttu-id="9a0d4-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-158">Byte</span><span class="sxs-lookup"><span data-stu-id="9a0d4-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="9a0d4-159">Columns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-159">Columns</span></span>

|<span data-ttu-id="9a0d4-160">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-160">ColumnName</span></span>|<span data-ttu-id="9a0d4-161">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9a0d4-162">TABLE_CAT</span></span>|<span data-ttu-id="9a0d4-163">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-163">String</span></span>|
|<span data-ttu-id="9a0d4-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9a0d4-164">TABLE_SCHEM</span></span>|<span data-ttu-id="9a0d4-165">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-165">String</span></span>|
|<span data-ttu-id="9a0d4-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-166">TABLE_NAME</span></span>|<span data-ttu-id="9a0d4-167">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-167">String</span></span>|
|<span data-ttu-id="9a0d4-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-168">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-169">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-169">String</span></span>|
|<span data-ttu-id="9a0d4-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-170">DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-171">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-171">Int16</span></span>|
|<span data-ttu-id="9a0d4-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-172">TYPE_NAME</span></span>|<span data-ttu-id="9a0d4-173">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-173">String</span></span>|
|<span data-ttu-id="9a0d4-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-174">COLUMN_SIZE</span></span>|<span data-ttu-id="9a0d4-175">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-175">Int32</span></span>|
|<span data-ttu-id="9a0d4-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="9a0d4-177">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-177">Int32</span></span>|
|<span data-ttu-id="9a0d4-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9a0d4-179">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-179">Int16</span></span>|
|<span data-ttu-id="9a0d4-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9a0d4-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9a0d4-181">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-181">Int16</span></span>|
|<span data-ttu-id="9a0d4-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-182">NULLABLE</span></span>|<span data-ttu-id="9a0d4-183">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-183">Int16</span></span>|
|<span data-ttu-id="9a0d4-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-184">REMARKS</span></span>|<span data-ttu-id="9a0d4-185">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-185">String</span></span>|
|<span data-ttu-id="9a0d4-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9a0d4-186">COLUMN_DEF</span></span>|<span data-ttu-id="9a0d4-187">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-187">String</span></span>|
|<span data-ttu-id="9a0d4-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-189">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-189">Int16</span></span>|
|<span data-ttu-id="9a0d4-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9a0d4-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9a0d4-191">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-191">Int16</span></span>|
|<span data-ttu-id="9a0d4-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9a0d4-193">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-193">Int32</span></span>|
|<span data-ttu-id="9a0d4-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-195">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-195">Int32</span></span>|
|<span data-ttu-id="9a0d4-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-196">IS_NULLABLE</span></span>|<span data-ttu-id="9a0d4-197">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-197">String</span></span>|
|<span data-ttu-id="9a0d4-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a0d4-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9a0d4-199">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-199">String</span></span>|
|<span data-ttu-id="9a0d4-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a0d4-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9a0d4-201">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-201">String</span></span>|
|<span data-ttu-id="9a0d4-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-203">Byte</span><span class="sxs-lookup"><span data-stu-id="9a0d4-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="9a0d4-204">절차</span><span class="sxs-lookup"><span data-stu-id="9a0d4-204">Procedures</span></span>

|<span data-ttu-id="9a0d4-205">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-205">ColumnName</span></span>|<span data-ttu-id="9a0d4-206">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9a0d4-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="9a0d4-208">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-208">String</span></span>|
|<span data-ttu-id="9a0d4-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9a0d4-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9a0d4-210">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-210">String</span></span>|
|<span data-ttu-id="9a0d4-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="9a0d4-212">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-212">String</span></span>|
|<span data-ttu-id="9a0d4-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9a0d4-214">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-214">Int32</span></span>|
|<span data-ttu-id="9a0d4-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9a0d4-216">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-216">Int32</span></span>|
|<span data-ttu-id="9a0d4-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9a0d4-218">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-218">Int32</span></span>|
|<span data-ttu-id="9a0d4-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-219">REMARKS</span></span>|<span data-ttu-id="9a0d4-220">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-220">String</span></span>|
|<span data-ttu-id="9a0d4-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9a0d4-222">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="9a0d4-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-223">ProcedureColumns</span></span>

|<span data-ttu-id="9a0d4-224">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-224">ColumnName</span></span>|<span data-ttu-id="9a0d4-225">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9a0d4-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="9a0d4-227">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-227">String</span></span>|
|<span data-ttu-id="9a0d4-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9a0d4-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9a0d4-229">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-229">String</span></span>|
|<span data-ttu-id="9a0d4-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="9a0d4-231">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-231">String</span></span>|
|<span data-ttu-id="9a0d4-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-232">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-233">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-233">String</span></span>|
|<span data-ttu-id="9a0d4-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-234">COLUMN_TYPE</span></span>|<span data-ttu-id="9a0d4-235">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-235">Int16</span></span>|
|<span data-ttu-id="9a0d4-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-236">DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-237">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-237">Int16</span></span>|
|<span data-ttu-id="9a0d4-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-238">TYPE_NAME</span></span>|<span data-ttu-id="9a0d4-239">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-239">String</span></span>|
|<span data-ttu-id="9a0d4-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-240">COLUMN_SIZE</span></span>|<span data-ttu-id="9a0d4-241">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-241">Int32</span></span>|
|<span data-ttu-id="9a0d4-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="9a0d4-243">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-243">Int32</span></span>|
|<span data-ttu-id="9a0d4-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9a0d4-245">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-245">Int16</span></span>|
|<span data-ttu-id="9a0d4-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9a0d4-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9a0d4-247">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-247">Int16</span></span>|
|<span data-ttu-id="9a0d4-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-248">NULLABLE</span></span>|<span data-ttu-id="9a0d4-249">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-249">Int16</span></span>|
|<span data-ttu-id="9a0d4-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-250">REMARKS</span></span>|<span data-ttu-id="9a0d4-251">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-251">String</span></span>|
|<span data-ttu-id="9a0d4-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9a0d4-252">COLUMN_DEF</span></span>|<span data-ttu-id="9a0d4-253">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-253">String</span></span>|
|<span data-ttu-id="9a0d4-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-255">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-255">Int16</span></span>|
|<span data-ttu-id="9a0d4-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9a0d4-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9a0d4-257">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-257">Int16</span></span>|
|<span data-ttu-id="9a0d4-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9a0d4-259">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-259">Int32</span></span>|
|<span data-ttu-id="9a0d4-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-261">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-261">Int32</span></span>|
|<span data-ttu-id="9a0d4-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-262">IS_NULLABLE</span></span>|<span data-ttu-id="9a0d4-263">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-263">String</span></span>|
|<span data-ttu-id="9a0d4-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a0d4-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9a0d4-265">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-265">String</span></span>|
|<span data-ttu-id="9a0d4-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a0d4-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9a0d4-267">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-267">String</span></span>|
|<span data-ttu-id="9a0d4-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-269">Byte</span><span class="sxs-lookup"><span data-stu-id="9a0d4-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="9a0d4-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9a0d4-270">ProcedureParameters</span></span>

|<span data-ttu-id="9a0d4-271">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-271">ColumnName</span></span>|<span data-ttu-id="9a0d4-272">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9a0d4-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="9a0d4-274">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-274">String</span></span>|
|<span data-ttu-id="9a0d4-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9a0d4-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9a0d4-276">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-276">String</span></span>|
|<span data-ttu-id="9a0d4-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="9a0d4-278">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-278">String</span></span>|
|<span data-ttu-id="9a0d4-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-279">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-280">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-280">String</span></span>|
|<span data-ttu-id="9a0d4-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-281">COLUMN_TYPE</span></span>|<span data-ttu-id="9a0d4-282">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-282">Int16</span></span>|
|<span data-ttu-id="9a0d4-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-283">DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-284">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-284">Int16</span></span>|
|<span data-ttu-id="9a0d4-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-285">TYPE_NAME</span></span>|<span data-ttu-id="9a0d4-286">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-286">String</span></span>|
|<span data-ttu-id="9a0d4-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-287">COLUMN_SIZE</span></span>|<span data-ttu-id="9a0d4-288">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-288">Int32</span></span>|
|<span data-ttu-id="9a0d4-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="9a0d4-290">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-290">Int32</span></span>|
|<span data-ttu-id="9a0d4-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9a0d4-292">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-292">Int16</span></span>|
|<span data-ttu-id="9a0d4-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9a0d4-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9a0d4-294">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-294">Int16</span></span>|
|<span data-ttu-id="9a0d4-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-295">NULLABLE</span></span>|<span data-ttu-id="9a0d4-296">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-296">Int16</span></span>|
|<span data-ttu-id="9a0d4-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-297">REMARKS</span></span>|<span data-ttu-id="9a0d4-298">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-298">String</span></span>|
|<span data-ttu-id="9a0d4-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9a0d4-299">COLUMN_DEF</span></span>|<span data-ttu-id="9a0d4-300">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-300">String</span></span>|
|<span data-ttu-id="9a0d4-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-302">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-302">Int16</span></span>|
|<span data-ttu-id="9a0d4-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9a0d4-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9a0d4-304">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-304">Int16</span></span>|
|<span data-ttu-id="9a0d4-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9a0d4-306">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-306">Int32</span></span>|
|<span data-ttu-id="9a0d4-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-308">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-308">Int32</span></span>|
|<span data-ttu-id="9a0d4-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-309">IS_NULLABLE</span></span>|<span data-ttu-id="9a0d4-310">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-310">String</span></span>|
|<span data-ttu-id="9a0d4-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a0d4-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9a0d4-312">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-312">String</span></span>|
|<span data-ttu-id="9a0d4-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a0d4-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9a0d4-314">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-314">String</span></span>|
|<span data-ttu-id="9a0d4-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-316">Byte</span><span class="sxs-lookup"><span data-stu-id="9a0d4-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="9a0d4-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="9a0d4-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="9a0d4-318">Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="9a0d4-319">Tables</span><span class="sxs-lookup"><span data-stu-id="9a0d4-319">Tables</span></span>

- <span data-ttu-id="9a0d4-320">Columns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-320">Columns</span></span>

- <span data-ttu-id="9a0d4-321">절차</span><span class="sxs-lookup"><span data-stu-id="9a0d4-321">Procedures</span></span>

- <span data-ttu-id="9a0d4-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-322">ProcedureColumns</span></span>

- <span data-ttu-id="9a0d4-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9a0d4-323">ProcedureParameters</span></span>

- <span data-ttu-id="9a0d4-324">보기</span><span class="sxs-lookup"><span data-stu-id="9a0d4-324">Views</span></span>

- <span data-ttu-id="9a0d4-325">인덱스</span><span class="sxs-lookup"><span data-stu-id="9a0d4-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="9a0d4-326">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="9a0d4-326">Tables and Views</span></span>

|<span data-ttu-id="9a0d4-327">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-327">ColumnName</span></span>|<span data-ttu-id="9a0d4-328">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-330">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-330">String</span></span>|
|<span data-ttu-id="9a0d4-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-331">TABLE_OWNER</span></span>|<span data-ttu-id="9a0d4-332">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-332">String</span></span>|
|<span data-ttu-id="9a0d4-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-333">TABLE_NAME</span></span>|<span data-ttu-id="9a0d4-334">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-334">String</span></span>|
|<span data-ttu-id="9a0d4-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-335">TABLE_TYPE</span></span>|<span data-ttu-id="9a0d4-336">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-336">String</span></span>|
|<span data-ttu-id="9a0d4-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-337">REMARKS</span></span>|<span data-ttu-id="9a0d4-338">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="9a0d4-339">Columns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-339">Columns</span></span>

|<span data-ttu-id="9a0d4-340">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-340">ColumnName</span></span>|<span data-ttu-id="9a0d4-341">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-343">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-343">String</span></span>|
|<span data-ttu-id="9a0d4-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-344">TABLE_OWNER</span></span>|<span data-ttu-id="9a0d4-345">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-345">String</span></span>|
|<span data-ttu-id="9a0d4-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-346">TABLE_NAME</span></span>|<span data-ttu-id="9a0d4-347">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-347">String</span></span>|
|<span data-ttu-id="9a0d4-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-348">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-349">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-349">String</span></span>|
|<span data-ttu-id="9a0d4-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-350">DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-351">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-351">Int16</span></span>|
|<span data-ttu-id="9a0d4-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-352">TYPE_NAME</span></span>|<span data-ttu-id="9a0d4-353">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-353">String</span></span>|
|<span data-ttu-id="9a0d4-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-354">PRECISION</span></span>|<span data-ttu-id="9a0d4-355">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-355">Int32</span></span>|
|<span data-ttu-id="9a0d4-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-356">LENGTH</span></span>|<span data-ttu-id="9a0d4-357">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-357">Int32</span></span>|
|<span data-ttu-id="9a0d4-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-358">SCALE</span></span>|<span data-ttu-id="9a0d4-359">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-359">Int16</span></span>|
|<span data-ttu-id="9a0d4-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="9a0d4-360">RADIX</span></span>|<span data-ttu-id="9a0d4-361">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-361">Int16</span></span>|
|<span data-ttu-id="9a0d4-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-362">NULLABLE</span></span>|<span data-ttu-id="9a0d4-363">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-363">Int16</span></span>|
|<span data-ttu-id="9a0d4-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-364">REMARKS</span></span>|<span data-ttu-id="9a0d4-365">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-365">String</span></span>|
|<span data-ttu-id="9a0d4-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-367">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="9a0d4-368">절차</span><span class="sxs-lookup"><span data-stu-id="9a0d4-368">Procedures</span></span>

|<span data-ttu-id="9a0d4-369">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-369">ColumnName</span></span>|<span data-ttu-id="9a0d4-370">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-372">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-372">String</span></span>|
|<span data-ttu-id="9a0d4-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9a0d4-374">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-374">String</span></span>|
|<span data-ttu-id="9a0d4-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="9a0d4-376">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-376">String</span></span>|
|<span data-ttu-id="9a0d4-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9a0d4-378">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-378">Int16</span></span>|
|<span data-ttu-id="9a0d4-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9a0d4-380">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-380">Int16</span></span>|
|<span data-ttu-id="9a0d4-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9a0d4-382">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-382">Int16</span></span>|
|<span data-ttu-id="9a0d4-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-383">REMARKS</span></span>|<span data-ttu-id="9a0d4-384">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-384">String</span></span>|
|<span data-ttu-id="9a0d4-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9a0d4-386">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="9a0d4-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-387">ProcedureColumns</span></span>

|<span data-ttu-id="9a0d4-388">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-388">ColumnName</span></span>|<span data-ttu-id="9a0d4-389">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-391">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-391">String</span></span>|
|<span data-ttu-id="9a0d4-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9a0d4-393">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-393">String</span></span>|
|<span data-ttu-id="9a0d4-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="9a0d4-395">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-395">String</span></span>|
|<span data-ttu-id="9a0d4-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-396">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-397">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-397">String</span></span>|
|<span data-ttu-id="9a0d4-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-398">COLUMN_TYPE</span></span>|<span data-ttu-id="9a0d4-399">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-399">Int16</span></span>|
|<span data-ttu-id="9a0d4-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-400">DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-401">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-401">Int16</span></span>|
|<span data-ttu-id="9a0d4-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-402">TYPE_NAME</span></span>|<span data-ttu-id="9a0d4-403">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-403">String</span></span>|
|<span data-ttu-id="9a0d4-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-404">PRECISION</span></span>|<span data-ttu-id="9a0d4-405">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-405">Int32</span></span>|
|<span data-ttu-id="9a0d4-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-406">LENGTH</span></span>|<span data-ttu-id="9a0d4-407">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-407">Int32</span></span>|
|<span data-ttu-id="9a0d4-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-408">SCALE</span></span>|<span data-ttu-id="9a0d4-409">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-409">Int16</span></span>|
|<span data-ttu-id="9a0d4-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="9a0d4-410">RADIX</span></span>|<span data-ttu-id="9a0d4-411">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-411">Int16</span></span>|
|<span data-ttu-id="9a0d4-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-412">NULLABLE</span></span>|<span data-ttu-id="9a0d4-413">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-413">Int16</span></span>|
|<span data-ttu-id="9a0d4-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-414">REMARKS</span></span>|<span data-ttu-id="9a0d4-415">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-415">String</span></span>|
|<span data-ttu-id="9a0d4-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9a0d4-416">OVERLOAD</span></span>|<span data-ttu-id="9a0d4-417">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-417">Int32</span></span>|
|<span data-ttu-id="9a0d4-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-419">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="9a0d4-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="9a0d4-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="9a0d4-421">Microsoft Jet ODBC Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="9a0d4-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="9a0d4-422">Tables</span><span class="sxs-lookup"><span data-stu-id="9a0d4-422">Tables</span></span>

- <span data-ttu-id="9a0d4-423">인덱스</span><span class="sxs-lookup"><span data-stu-id="9a0d4-423">Indexes</span></span>

- <span data-ttu-id="9a0d4-424">Columns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-424">Columns</span></span>

- <span data-ttu-id="9a0d4-425">절차</span><span class="sxs-lookup"><span data-stu-id="9a0d4-425">Procedures</span></span>

- <span data-ttu-id="9a0d4-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-426">ProcedureColumns</span></span>

- <span data-ttu-id="9a0d4-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9a0d4-427">ProcedureParameters</span></span>

- <span data-ttu-id="9a0d4-428">보기</span><span class="sxs-lookup"><span data-stu-id="9a0d4-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="9a0d4-429">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="9a0d4-429">Tables and Views</span></span>

|<span data-ttu-id="9a0d4-430">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-430">ColumnName</span></span>|<span data-ttu-id="9a0d4-431">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-433">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-433">String</span></span>|
|<span data-ttu-id="9a0d4-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-434">TABLE_OWNER</span></span>|<span data-ttu-id="9a0d4-435">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-435">String</span></span>|
|<span data-ttu-id="9a0d4-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-436">TABLE_NAME</span></span>|<span data-ttu-id="9a0d4-437">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-437">String</span></span>|
|<span data-ttu-id="9a0d4-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-438">TABLE_TYPE</span></span>|<span data-ttu-id="9a0d4-439">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-439">String</span></span>|
|<span data-ttu-id="9a0d4-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-440">REMARKS</span></span>|<span data-ttu-id="9a0d4-441">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="9a0d4-442">Columns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-442">Columns</span></span>

|<span data-ttu-id="9a0d4-443">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-443">ColumnName</span></span>|<span data-ttu-id="9a0d4-444">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-446">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-446">String</span></span>|
|<span data-ttu-id="9a0d4-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-447">TABLE_OWNER</span></span>|<span data-ttu-id="9a0d4-448">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-448">String</span></span>|
|<span data-ttu-id="9a0d4-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-449">TABLE_NAME</span></span>|<span data-ttu-id="9a0d4-450">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-450">String</span></span>|
|<span data-ttu-id="9a0d4-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-451">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-452">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-452">String</span></span>|
|<span data-ttu-id="9a0d4-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-453">DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-454">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-454">Int16</span></span>|
|<span data-ttu-id="9a0d4-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-455">TYPE_NAME</span></span>|<span data-ttu-id="9a0d4-456">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-456">String</span></span>|
|<span data-ttu-id="9a0d4-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-457">PRECISION</span></span>|<span data-ttu-id="9a0d4-458">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-458">Int32</span></span>|
|<span data-ttu-id="9a0d4-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-459">LENGTH</span></span>|<span data-ttu-id="9a0d4-460">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-460">Int32</span></span>|
|<span data-ttu-id="9a0d4-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-461">SCALE</span></span>|<span data-ttu-id="9a0d4-462">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-462">Int16</span></span>|
|<span data-ttu-id="9a0d4-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="9a0d4-463">RADIX</span></span>|<span data-ttu-id="9a0d4-464">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-464">Int16</span></span>|
|<span data-ttu-id="9a0d4-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-465">NULLABLE</span></span>|<span data-ttu-id="9a0d4-466">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-466">Int16</span></span>|
|<span data-ttu-id="9a0d4-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-467">REMARKS</span></span>|<span data-ttu-id="9a0d4-468">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-468">String</span></span>|
|<span data-ttu-id="9a0d4-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-470">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="9a0d4-471">절차</span><span class="sxs-lookup"><span data-stu-id="9a0d4-471">Procedures</span></span>

|<span data-ttu-id="9a0d4-472">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-472">ColumnName</span></span>|<span data-ttu-id="9a0d4-473">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-475">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-475">String</span></span>|
|<span data-ttu-id="9a0d4-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9a0d4-477">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-477">String</span></span>|
|<span data-ttu-id="9a0d4-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="9a0d4-479">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-479">String</span></span>|
|<span data-ttu-id="9a0d4-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9a0d4-481">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-481">Int16</span></span>|
|<span data-ttu-id="9a0d4-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9a0d4-483">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-483">Int16</span></span>|
|<span data-ttu-id="9a0d4-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9a0d4-485">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-485">Int16</span></span>|
|<span data-ttu-id="9a0d4-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-486">REMARKS</span></span>|<span data-ttu-id="9a0d4-487">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-487">String</span></span>|
|<span data-ttu-id="9a0d4-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9a0d4-489">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="9a0d4-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9a0d4-490">ProcedureColumns</span></span>

|<span data-ttu-id="9a0d4-491">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-491">ColumnName</span></span>|<span data-ttu-id="9a0d4-492">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9a0d4-494">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-494">String</span></span>|
|<span data-ttu-id="9a0d4-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a0d4-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9a0d4-496">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-496">String</span></span>|
|<span data-ttu-id="9a0d4-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="9a0d4-498">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-498">String</span></span>|
|<span data-ttu-id="9a0d4-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-499">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-500">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-500">String</span></span>|
|<span data-ttu-id="9a0d4-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-501">COLUMN_TYPE</span></span>|<span data-ttu-id="9a0d4-502">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-502">Int16</span></span>|
|<span data-ttu-id="9a0d4-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-503">DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-504">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-504">Int16</span></span>|
|<span data-ttu-id="9a0d4-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-505">TYPE_NAME</span></span>|<span data-ttu-id="9a0d4-506">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-506">String</span></span>|
|<span data-ttu-id="9a0d4-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-507">PRECISION</span></span>|<span data-ttu-id="9a0d4-508">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-508">Int32</span></span>|
|<span data-ttu-id="9a0d4-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-509">LENGTH</span></span>|<span data-ttu-id="9a0d4-510">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-510">Int32</span></span>|
|<span data-ttu-id="9a0d4-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-511">SCALE</span></span>|<span data-ttu-id="9a0d4-512">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-512">Int16</span></span>|
|<span data-ttu-id="9a0d4-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="9a0d4-513">RADIX</span></span>|<span data-ttu-id="9a0d4-514">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-514">Int16</span></span>|
|<span data-ttu-id="9a0d4-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-515">NULLABLE</span></span>|<span data-ttu-id="9a0d4-516">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-516">Int16</span></span>|
|<span data-ttu-id="9a0d4-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-517">REMARKS</span></span>|<span data-ttu-id="9a0d4-518">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-518">String</span></span>|
|<span data-ttu-id="9a0d4-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9a0d4-519">OVERLOAD</span></span>|<span data-ttu-id="9a0d4-520">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-520">Int32</span></span>|
|<span data-ttu-id="9a0d4-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-522">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="9a0d4-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9a0d4-523">ProcedureParameters</span></span>

|<span data-ttu-id="9a0d4-524">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a0d4-524">ColumnName</span></span>|<span data-ttu-id="9a0d4-525">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a0d4-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="9a0d4-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9a0d4-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="9a0d4-527">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-527">String</span></span>|
|<span data-ttu-id="9a0d4-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9a0d4-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9a0d4-529">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-529">String</span></span>|
|<span data-ttu-id="9a0d4-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="9a0d4-531">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-531">String</span></span>|
|<span data-ttu-id="9a0d4-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-532">COLUMN_NAME</span></span>|<span data-ttu-id="9a0d4-533">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-533">String</span></span>|
|<span data-ttu-id="9a0d4-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-534">COLUMN_TYPE</span></span>|<span data-ttu-id="9a0d4-535">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-535">Int16</span></span>|
|<span data-ttu-id="9a0d4-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-536">DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-537">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-537">Int16</span></span>|
|<span data-ttu-id="9a0d4-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a0d4-538">TYPE_NAME</span></span>|<span data-ttu-id="9a0d4-539">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-539">String</span></span>|
|<span data-ttu-id="9a0d4-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-540">COLUMN_SIZE</span></span>|<span data-ttu-id="9a0d4-541">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-541">Int32</span></span>|
|<span data-ttu-id="9a0d4-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="9a0d4-543">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-543">Int32</span></span>|
|<span data-ttu-id="9a0d4-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9a0d4-545">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-545">Int16</span></span>|
|<span data-ttu-id="9a0d4-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9a0d4-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9a0d4-547">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-547">Int16</span></span>|
|<span data-ttu-id="9a0d4-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-548">NULLABLE</span></span>|<span data-ttu-id="9a0d4-549">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-549">Int16</span></span>|
|<span data-ttu-id="9a0d4-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9a0d4-550">REMARKS</span></span>|<span data-ttu-id="9a0d4-551">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-551">String</span></span>|
|<span data-ttu-id="9a0d4-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9a0d4-552">COLUMN_DEF</span></span>|<span data-ttu-id="9a0d4-553">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-553">String</span></span>|
|<span data-ttu-id="9a0d4-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9a0d4-555">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-555">Int16</span></span>|
|<span data-ttu-id="9a0d4-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9a0d4-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9a0d4-557">Int16</span><span class="sxs-lookup"><span data-stu-id="9a0d4-557">Int16</span></span>|
|<span data-ttu-id="9a0d4-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9a0d4-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9a0d4-559">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-559">Int32</span></span>|
|<span data-ttu-id="9a0d4-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9a0d4-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="9a0d4-561">Int32</span><span class="sxs-lookup"><span data-stu-id="9a0d4-561">Int32</span></span>|
|<span data-ttu-id="9a0d4-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9a0d4-562">IS_NULLABLE</span></span>|<span data-ttu-id="9a0d4-563">문자열</span><span class="sxs-lookup"><span data-stu-id="9a0d4-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="9a0d4-564">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a0d4-564">See also</span></span>

- [<span data-ttu-id="9a0d4-565">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="9a0d4-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
