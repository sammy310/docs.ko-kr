---
title: ODBC 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794726"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="8af46-102">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="8af46-102">ODBC Schema Collections</span></span>

<span data-ttu-id="8af46-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8af46-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="8af46-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="8af46-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="8af46-105">Microsoft SQL Server ODBC 드라이버는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8af46-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="8af46-106">테이블</span><span class="sxs-lookup"><span data-stu-id="8af46-106">Tables</span></span>

- <span data-ttu-id="8af46-107">인덱스</span><span class="sxs-lookup"><span data-stu-id="8af46-107">Indexes</span></span>

- <span data-ttu-id="8af46-108">열</span><span class="sxs-lookup"><span data-stu-id="8af46-108">Columns</span></span>

- <span data-ttu-id="8af46-109">절차</span><span class="sxs-lookup"><span data-stu-id="8af46-109">Procedures</span></span>

- <span data-ttu-id="8af46-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8af46-110">ProcedureColumns</span></span>

- <span data-ttu-id="8af46-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8af46-111">ProcedureParameters</span></span>

- <span data-ttu-id="8af46-112">뷰</span><span class="sxs-lookup"><span data-stu-id="8af46-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="8af46-113">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="8af46-113">Tables and Views</span></span>

|<span data-ttu-id="8af46-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-114">ColumnName</span></span>|<span data-ttu-id="8af46-115">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="8af46-116">TABLE_CAT</span></span>|<span data-ttu-id="8af46-117">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-117">String</span></span>|
|<span data-ttu-id="8af46-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8af46-118">TABLE_SCHEM</span></span>|<span data-ttu-id="8af46-119">String</span><span class="sxs-lookup"><span data-stu-id="8af46-119">String</span></span>|
|<span data-ttu-id="8af46-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-120">TABLE_NAME</span></span>|<span data-ttu-id="8af46-121">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-121">String</span></span>|
|<span data-ttu-id="8af46-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-122">TABLE_TYPE</span></span>|<span data-ttu-id="8af46-123">String</span><span class="sxs-lookup"><span data-stu-id="8af46-123">String</span></span>|
|<span data-ttu-id="8af46-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-124">REMARKS</span></span>|<span data-ttu-id="8af46-125">String</span><span class="sxs-lookup"><span data-stu-id="8af46-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="8af46-126">인덱스</span><span class="sxs-lookup"><span data-stu-id="8af46-126">Indexes</span></span>

|<span data-ttu-id="8af46-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-127">ColumnName</span></span>|<span data-ttu-id="8af46-128">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="8af46-129">TABLE_CAT</span></span>|<span data-ttu-id="8af46-130">String</span><span class="sxs-lookup"><span data-stu-id="8af46-130">String</span></span>|
|<span data-ttu-id="8af46-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8af46-131">TABLE_SCHEM</span></span>|<span data-ttu-id="8af46-132">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-132">String</span></span>|
|<span data-ttu-id="8af46-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-133">TABLE_NAME</span></span>|<span data-ttu-id="8af46-134">String</span><span class="sxs-lookup"><span data-stu-id="8af46-134">String</span></span>|
|<span data-ttu-id="8af46-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="8af46-135">NON_UNIQUE</span></span>|<span data-ttu-id="8af46-136">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-136">Int16</span></span>|
|<span data-ttu-id="8af46-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="8af46-138">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-138">String</span></span>|
|<span data-ttu-id="8af46-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-139">INDEX_NAME</span></span>|<span data-ttu-id="8af46-140">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-140">String</span></span>|
|<span data-ttu-id="8af46-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-141">TYPE</span></span>|<span data-ttu-id="8af46-142">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-142">Int16</span></span>|
|<span data-ttu-id="8af46-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-144">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-144">Int16</span></span>|
|<span data-ttu-id="8af46-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-145">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-146">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-146">String</span></span>|
|<span data-ttu-id="8af46-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="8af46-147">ASC_OR_DESC</span></span>|<span data-ttu-id="8af46-148">String</span><span class="sxs-lookup"><span data-stu-id="8af46-148">String</span></span>|
|<span data-ttu-id="8af46-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="8af46-149">CARDINALITY</span></span>|<span data-ttu-id="8af46-150">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-150">Int32</span></span>|
|<span data-ttu-id="8af46-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="8af46-151">PAGES</span></span>|<span data-ttu-id="8af46-152">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-152">Int32</span></span>|
|<span data-ttu-id="8af46-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="8af46-153">FILTER_CONDITION</span></span>|<span data-ttu-id="8af46-154">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-154">String</span></span>|
|<span data-ttu-id="8af46-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8af46-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="8af46-156">String</span><span class="sxs-lookup"><span data-stu-id="8af46-156">String</span></span>|
|<span data-ttu-id="8af46-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="8af46-158">Byte</span><span class="sxs-lookup"><span data-stu-id="8af46-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="8af46-159">열</span><span class="sxs-lookup"><span data-stu-id="8af46-159">Columns</span></span>

|<span data-ttu-id="8af46-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-160">ColumnName</span></span>|<span data-ttu-id="8af46-161">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="8af46-162">TABLE_CAT</span></span>|<span data-ttu-id="8af46-163">String</span><span class="sxs-lookup"><span data-stu-id="8af46-163">String</span></span>|
|<span data-ttu-id="8af46-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8af46-164">TABLE_SCHEM</span></span>|<span data-ttu-id="8af46-165">String</span><span class="sxs-lookup"><span data-stu-id="8af46-165">String</span></span>|
|<span data-ttu-id="8af46-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-166">TABLE_NAME</span></span>|<span data-ttu-id="8af46-167">String</span><span class="sxs-lookup"><span data-stu-id="8af46-167">String</span></span>|
|<span data-ttu-id="8af46-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-168">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-169">String</span><span class="sxs-lookup"><span data-stu-id="8af46-169">String</span></span>|
|<span data-ttu-id="8af46-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-170">DATA_TYPE</span></span>|<span data-ttu-id="8af46-171">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-171">Int16</span></span>|
|<span data-ttu-id="8af46-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-172">TYPE_NAME</span></span>|<span data-ttu-id="8af46-173">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-173">String</span></span>|
|<span data-ttu-id="8af46-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="8af46-174">COLUMN_SIZE</span></span>|<span data-ttu-id="8af46-175">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-175">Int32</span></span>|
|<span data-ttu-id="8af46-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="8af46-177">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-177">Int32</span></span>|
|<span data-ttu-id="8af46-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="8af46-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="8af46-179">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-179">Int16</span></span>|
|<span data-ttu-id="8af46-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="8af46-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="8af46-181">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-181">Int16</span></span>|
|<span data-ttu-id="8af46-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-182">NULLABLE</span></span>|<span data-ttu-id="8af46-183">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-183">Int16</span></span>|
|<span data-ttu-id="8af46-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-184">REMARKS</span></span>|<span data-ttu-id="8af46-185">String</span><span class="sxs-lookup"><span data-stu-id="8af46-185">String</span></span>|
|<span data-ttu-id="8af46-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="8af46-186">COLUMN_DEF</span></span>|<span data-ttu-id="8af46-187">String</span><span class="sxs-lookup"><span data-stu-id="8af46-187">String</span></span>|
|<span data-ttu-id="8af46-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="8af46-189">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-189">Int16</span></span>|
|<span data-ttu-id="8af46-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="8af46-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="8af46-191">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-191">Int16</span></span>|
|<span data-ttu-id="8af46-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="8af46-193">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-193">Int32</span></span>|
|<span data-ttu-id="8af46-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-195">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-195">Int32</span></span>|
|<span data-ttu-id="8af46-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-196">IS_NULLABLE</span></span>|<span data-ttu-id="8af46-197">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-197">String</span></span>|
|<span data-ttu-id="8af46-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8af46-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="8af46-199">String</span><span class="sxs-lookup"><span data-stu-id="8af46-199">String</span></span>|
|<span data-ttu-id="8af46-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8af46-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="8af46-201">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-201">String</span></span>|
|<span data-ttu-id="8af46-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="8af46-203">Byte</span><span class="sxs-lookup"><span data-stu-id="8af46-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="8af46-204">절차</span><span class="sxs-lookup"><span data-stu-id="8af46-204">Procedures</span></span>

|<span data-ttu-id="8af46-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-205">ColumnName</span></span>|<span data-ttu-id="8af46-206">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="8af46-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="8af46-208">String</span><span class="sxs-lookup"><span data-stu-id="8af46-208">String</span></span>|
|<span data-ttu-id="8af46-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8af46-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="8af46-210">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-210">String</span></span>|
|<span data-ttu-id="8af46-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="8af46-212">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-212">String</span></span>|
|<span data-ttu-id="8af46-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8af46-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="8af46-214">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-214">Int32</span></span>|
|<span data-ttu-id="8af46-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8af46-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="8af46-216">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-216">Int32</span></span>|
|<span data-ttu-id="8af46-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="8af46-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="8af46-218">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-218">Int32</span></span>|
|<span data-ttu-id="8af46-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-219">REMARKS</span></span>|<span data-ttu-id="8af46-220">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-220">String</span></span>|
|<span data-ttu-id="8af46-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8af46-222">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="8af46-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8af46-223">ProcedureColumns</span></span>

|<span data-ttu-id="8af46-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-224">ColumnName</span></span>|<span data-ttu-id="8af46-225">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="8af46-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="8af46-227">String</span><span class="sxs-lookup"><span data-stu-id="8af46-227">String</span></span>|
|<span data-ttu-id="8af46-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8af46-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="8af46-229">String</span><span class="sxs-lookup"><span data-stu-id="8af46-229">String</span></span>|
|<span data-ttu-id="8af46-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="8af46-231">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-231">String</span></span>|
|<span data-ttu-id="8af46-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-232">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-233">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-233">String</span></span>|
|<span data-ttu-id="8af46-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-234">COLUMN_TYPE</span></span>|<span data-ttu-id="8af46-235">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-235">Int16</span></span>|
|<span data-ttu-id="8af46-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-236">DATA_TYPE</span></span>|<span data-ttu-id="8af46-237">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-237">Int16</span></span>|
|<span data-ttu-id="8af46-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-238">TYPE_NAME</span></span>|<span data-ttu-id="8af46-239">String</span><span class="sxs-lookup"><span data-stu-id="8af46-239">String</span></span>|
|<span data-ttu-id="8af46-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="8af46-240">COLUMN_SIZE</span></span>|<span data-ttu-id="8af46-241">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-241">Int32</span></span>|
|<span data-ttu-id="8af46-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="8af46-243">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-243">Int32</span></span>|
|<span data-ttu-id="8af46-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="8af46-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="8af46-245">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-245">Int16</span></span>|
|<span data-ttu-id="8af46-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="8af46-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="8af46-247">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-247">Int16</span></span>|
|<span data-ttu-id="8af46-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-248">NULLABLE</span></span>|<span data-ttu-id="8af46-249">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-249">Int16</span></span>|
|<span data-ttu-id="8af46-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-250">REMARKS</span></span>|<span data-ttu-id="8af46-251">String</span><span class="sxs-lookup"><span data-stu-id="8af46-251">String</span></span>|
|<span data-ttu-id="8af46-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="8af46-252">COLUMN_DEF</span></span>|<span data-ttu-id="8af46-253">String</span><span class="sxs-lookup"><span data-stu-id="8af46-253">String</span></span>|
|<span data-ttu-id="8af46-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="8af46-255">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-255">Int16</span></span>|
|<span data-ttu-id="8af46-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="8af46-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="8af46-257">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-257">Int16</span></span>|
|<span data-ttu-id="8af46-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="8af46-259">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-259">Int32</span></span>|
|<span data-ttu-id="8af46-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-261">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-261">Int32</span></span>|
|<span data-ttu-id="8af46-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-262">IS_NULLABLE</span></span>|<span data-ttu-id="8af46-263">String</span><span class="sxs-lookup"><span data-stu-id="8af46-263">String</span></span>|
|<span data-ttu-id="8af46-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8af46-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="8af46-265">String</span><span class="sxs-lookup"><span data-stu-id="8af46-265">String</span></span>|
|<span data-ttu-id="8af46-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8af46-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="8af46-267">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-267">String</span></span>|
|<span data-ttu-id="8af46-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="8af46-269">Byte</span><span class="sxs-lookup"><span data-stu-id="8af46-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="8af46-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8af46-270">ProcedureParameters</span></span>

|<span data-ttu-id="8af46-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-271">ColumnName</span></span>|<span data-ttu-id="8af46-272">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="8af46-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="8af46-274">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-274">String</span></span>|
|<span data-ttu-id="8af46-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8af46-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="8af46-276">String</span><span class="sxs-lookup"><span data-stu-id="8af46-276">String</span></span>|
|<span data-ttu-id="8af46-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="8af46-278">String</span><span class="sxs-lookup"><span data-stu-id="8af46-278">String</span></span>|
|<span data-ttu-id="8af46-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-279">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-280">String</span><span class="sxs-lookup"><span data-stu-id="8af46-280">String</span></span>|
|<span data-ttu-id="8af46-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-281">COLUMN_TYPE</span></span>|<span data-ttu-id="8af46-282">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-282">Int16</span></span>|
|<span data-ttu-id="8af46-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-283">DATA_TYPE</span></span>|<span data-ttu-id="8af46-284">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-284">Int16</span></span>|
|<span data-ttu-id="8af46-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-285">TYPE_NAME</span></span>|<span data-ttu-id="8af46-286">String</span><span class="sxs-lookup"><span data-stu-id="8af46-286">String</span></span>|
|<span data-ttu-id="8af46-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="8af46-287">COLUMN_SIZE</span></span>|<span data-ttu-id="8af46-288">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-288">Int32</span></span>|
|<span data-ttu-id="8af46-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="8af46-290">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-290">Int32</span></span>|
|<span data-ttu-id="8af46-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="8af46-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="8af46-292">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-292">Int16</span></span>|
|<span data-ttu-id="8af46-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="8af46-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="8af46-294">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-294">Int16</span></span>|
|<span data-ttu-id="8af46-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-295">NULLABLE</span></span>|<span data-ttu-id="8af46-296">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-296">Int16</span></span>|
|<span data-ttu-id="8af46-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-297">REMARKS</span></span>|<span data-ttu-id="8af46-298">String</span><span class="sxs-lookup"><span data-stu-id="8af46-298">String</span></span>|
|<span data-ttu-id="8af46-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="8af46-299">COLUMN_DEF</span></span>|<span data-ttu-id="8af46-300">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-300">String</span></span>|
|<span data-ttu-id="8af46-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="8af46-302">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-302">Int16</span></span>|
|<span data-ttu-id="8af46-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="8af46-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="8af46-304">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-304">Int16</span></span>|
|<span data-ttu-id="8af46-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="8af46-306">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-306">Int32</span></span>|
|<span data-ttu-id="8af46-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-308">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-308">Int32</span></span>|
|<span data-ttu-id="8af46-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-309">IS_NULLABLE</span></span>|<span data-ttu-id="8af46-310">String</span><span class="sxs-lookup"><span data-stu-id="8af46-310">String</span></span>|
|<span data-ttu-id="8af46-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8af46-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="8af46-312">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-312">String</span></span>|
|<span data-ttu-id="8af46-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8af46-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="8af46-314">String</span><span class="sxs-lookup"><span data-stu-id="8af46-314">String</span></span>|
|<span data-ttu-id="8af46-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="8af46-316">Byte</span><span class="sxs-lookup"><span data-stu-id="8af46-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="8af46-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="8af46-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="8af46-318">Microsoft SQL Server Oracle ODBC 드라이버는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8af46-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="8af46-319">테이블</span><span class="sxs-lookup"><span data-stu-id="8af46-319">Tables</span></span>

- <span data-ttu-id="8af46-320">열</span><span class="sxs-lookup"><span data-stu-id="8af46-320">Columns</span></span>

- <span data-ttu-id="8af46-321">절차</span><span class="sxs-lookup"><span data-stu-id="8af46-321">Procedures</span></span>

- <span data-ttu-id="8af46-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8af46-322">ProcedureColumns</span></span>

- <span data-ttu-id="8af46-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8af46-323">ProcedureParameters</span></span>

- <span data-ttu-id="8af46-324">뷰</span><span class="sxs-lookup"><span data-stu-id="8af46-324">Views</span></span>

- <span data-ttu-id="8af46-325">인덱스</span><span class="sxs-lookup"><span data-stu-id="8af46-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="8af46-326">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="8af46-326">Tables and Views</span></span>

|<span data-ttu-id="8af46-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-327">ColumnName</span></span>|<span data-ttu-id="8af46-328">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="8af46-330">String</span><span class="sxs-lookup"><span data-stu-id="8af46-330">String</span></span>|
|<span data-ttu-id="8af46-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af46-331">TABLE_OWNER</span></span>|<span data-ttu-id="8af46-332">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-332">String</span></span>|
|<span data-ttu-id="8af46-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-333">TABLE_NAME</span></span>|<span data-ttu-id="8af46-334">String</span><span class="sxs-lookup"><span data-stu-id="8af46-334">String</span></span>|
|<span data-ttu-id="8af46-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-335">TABLE_TYPE</span></span>|<span data-ttu-id="8af46-336">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-336">String</span></span>|
|<span data-ttu-id="8af46-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-337">REMARKS</span></span>|<span data-ttu-id="8af46-338">String</span><span class="sxs-lookup"><span data-stu-id="8af46-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="8af46-339">열</span><span class="sxs-lookup"><span data-stu-id="8af46-339">Columns</span></span>

|<span data-ttu-id="8af46-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-340">ColumnName</span></span>|<span data-ttu-id="8af46-341">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="8af46-343">String</span><span class="sxs-lookup"><span data-stu-id="8af46-343">String</span></span>|
|<span data-ttu-id="8af46-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af46-344">TABLE_OWNER</span></span>|<span data-ttu-id="8af46-345">String</span><span class="sxs-lookup"><span data-stu-id="8af46-345">String</span></span>|
|<span data-ttu-id="8af46-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-346">TABLE_NAME</span></span>|<span data-ttu-id="8af46-347">String</span><span class="sxs-lookup"><span data-stu-id="8af46-347">String</span></span>|
|<span data-ttu-id="8af46-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-348">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-349">String</span><span class="sxs-lookup"><span data-stu-id="8af46-349">String</span></span>|
|<span data-ttu-id="8af46-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-350">DATA_TYPE</span></span>|<span data-ttu-id="8af46-351">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-351">Int16</span></span>|
|<span data-ttu-id="8af46-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-352">TYPE_NAME</span></span>|<span data-ttu-id="8af46-353">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-353">String</span></span>|
|<span data-ttu-id="8af46-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="8af46-354">PRECISION</span></span>|<span data-ttu-id="8af46-355">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-355">Int32</span></span>|
|<span data-ttu-id="8af46-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-356">LENGTH</span></span>|<span data-ttu-id="8af46-357">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-357">Int32</span></span>|
|<span data-ttu-id="8af46-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="8af46-358">SCALE</span></span>|<span data-ttu-id="8af46-359">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-359">Int16</span></span>|
|<span data-ttu-id="8af46-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="8af46-360">RADIX</span></span>|<span data-ttu-id="8af46-361">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-361">Int16</span></span>|
|<span data-ttu-id="8af46-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-362">NULLABLE</span></span>|<span data-ttu-id="8af46-363">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-363">Int16</span></span>|
|<span data-ttu-id="8af46-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-364">REMARKS</span></span>|<span data-ttu-id="8af46-365">String</span><span class="sxs-lookup"><span data-stu-id="8af46-365">String</span></span>|
|<span data-ttu-id="8af46-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-367">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="8af46-368">절차</span><span class="sxs-lookup"><span data-stu-id="8af46-368">Procedures</span></span>

|<span data-ttu-id="8af46-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-369">ColumnName</span></span>|<span data-ttu-id="8af46-370">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="8af46-372">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-372">String</span></span>|
|<span data-ttu-id="8af46-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af46-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="8af46-374">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-374">String</span></span>|
|<span data-ttu-id="8af46-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="8af46-376">String</span><span class="sxs-lookup"><span data-stu-id="8af46-376">String</span></span>|
|<span data-ttu-id="8af46-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8af46-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="8af46-378">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-378">Int16</span></span>|
|<span data-ttu-id="8af46-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8af46-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="8af46-380">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-380">Int16</span></span>|
|<span data-ttu-id="8af46-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="8af46-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="8af46-382">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-382">Int16</span></span>|
|<span data-ttu-id="8af46-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-383">REMARKS</span></span>|<span data-ttu-id="8af46-384">String</span><span class="sxs-lookup"><span data-stu-id="8af46-384">String</span></span>|
|<span data-ttu-id="8af46-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8af46-386">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="8af46-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8af46-387">ProcedureColumns</span></span>

|<span data-ttu-id="8af46-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-388">ColumnName</span></span>|<span data-ttu-id="8af46-389">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="8af46-391">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-391">String</span></span>|
|<span data-ttu-id="8af46-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af46-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="8af46-393">String</span><span class="sxs-lookup"><span data-stu-id="8af46-393">String</span></span>|
|<span data-ttu-id="8af46-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="8af46-395">String</span><span class="sxs-lookup"><span data-stu-id="8af46-395">String</span></span>|
|<span data-ttu-id="8af46-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-396">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-397">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-397">String</span></span>|
|<span data-ttu-id="8af46-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-398">COLUMN_TYPE</span></span>|<span data-ttu-id="8af46-399">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-399">Int16</span></span>|
|<span data-ttu-id="8af46-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-400">DATA_TYPE</span></span>|<span data-ttu-id="8af46-401">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-401">Int16</span></span>|
|<span data-ttu-id="8af46-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-402">TYPE_NAME</span></span>|<span data-ttu-id="8af46-403">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-403">String</span></span>|
|<span data-ttu-id="8af46-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="8af46-404">PRECISION</span></span>|<span data-ttu-id="8af46-405">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-405">Int32</span></span>|
|<span data-ttu-id="8af46-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-406">LENGTH</span></span>|<span data-ttu-id="8af46-407">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-407">Int32</span></span>|
|<span data-ttu-id="8af46-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="8af46-408">SCALE</span></span>|<span data-ttu-id="8af46-409">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-409">Int16</span></span>|
|<span data-ttu-id="8af46-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="8af46-410">RADIX</span></span>|<span data-ttu-id="8af46-411">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-411">Int16</span></span>|
|<span data-ttu-id="8af46-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-412">NULLABLE</span></span>|<span data-ttu-id="8af46-413">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-413">Int16</span></span>|
|<span data-ttu-id="8af46-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-414">REMARKS</span></span>|<span data-ttu-id="8af46-415">String</span><span class="sxs-lookup"><span data-stu-id="8af46-415">String</span></span>|
|<span data-ttu-id="8af46-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="8af46-416">OVERLOAD</span></span>|<span data-ttu-id="8af46-417">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-417">Int32</span></span>|
|<span data-ttu-id="8af46-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-419">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="8af46-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="8af46-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="8af46-421">Microsoft Jet ODBC Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="8af46-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="8af46-422">테이블</span><span class="sxs-lookup"><span data-stu-id="8af46-422">Tables</span></span>

- <span data-ttu-id="8af46-423">인덱스</span><span class="sxs-lookup"><span data-stu-id="8af46-423">Indexes</span></span>

- <span data-ttu-id="8af46-424">열</span><span class="sxs-lookup"><span data-stu-id="8af46-424">Columns</span></span>

- <span data-ttu-id="8af46-425">절차</span><span class="sxs-lookup"><span data-stu-id="8af46-425">Procedures</span></span>

- <span data-ttu-id="8af46-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8af46-426">ProcedureColumns</span></span>

- <span data-ttu-id="8af46-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8af46-427">ProcedureParameters</span></span>

- <span data-ttu-id="8af46-428">뷰</span><span class="sxs-lookup"><span data-stu-id="8af46-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="8af46-429">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="8af46-429">Tables and Views</span></span>

|<span data-ttu-id="8af46-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-430">ColumnName</span></span>|<span data-ttu-id="8af46-431">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="8af46-433">String</span><span class="sxs-lookup"><span data-stu-id="8af46-433">String</span></span>|
|<span data-ttu-id="8af46-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af46-434">TABLE_OWNER</span></span>|<span data-ttu-id="8af46-435">String</span><span class="sxs-lookup"><span data-stu-id="8af46-435">String</span></span>|
|<span data-ttu-id="8af46-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-436">TABLE_NAME</span></span>|<span data-ttu-id="8af46-437">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-437">String</span></span>|
|<span data-ttu-id="8af46-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-438">TABLE_TYPE</span></span>|<span data-ttu-id="8af46-439">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-439">String</span></span>|
|<span data-ttu-id="8af46-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-440">REMARKS</span></span>|<span data-ttu-id="8af46-441">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="8af46-442">열</span><span class="sxs-lookup"><span data-stu-id="8af46-442">Columns</span></span>

|<span data-ttu-id="8af46-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-443">ColumnName</span></span>|<span data-ttu-id="8af46-444">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="8af46-446">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-446">String</span></span>|
|<span data-ttu-id="8af46-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af46-447">TABLE_OWNER</span></span>|<span data-ttu-id="8af46-448">String</span><span class="sxs-lookup"><span data-stu-id="8af46-448">String</span></span>|
|<span data-ttu-id="8af46-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-449">TABLE_NAME</span></span>|<span data-ttu-id="8af46-450">String</span><span class="sxs-lookup"><span data-stu-id="8af46-450">String</span></span>|
|<span data-ttu-id="8af46-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-451">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-452">String</span><span class="sxs-lookup"><span data-stu-id="8af46-452">String</span></span>|
|<span data-ttu-id="8af46-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-453">DATA_TYPE</span></span>|<span data-ttu-id="8af46-454">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-454">Int16</span></span>|
|<span data-ttu-id="8af46-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-455">TYPE_NAME</span></span>|<span data-ttu-id="8af46-456">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-456">String</span></span>|
|<span data-ttu-id="8af46-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="8af46-457">PRECISION</span></span>|<span data-ttu-id="8af46-458">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-458">Int32</span></span>|
|<span data-ttu-id="8af46-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-459">LENGTH</span></span>|<span data-ttu-id="8af46-460">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-460">Int32</span></span>|
|<span data-ttu-id="8af46-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="8af46-461">SCALE</span></span>|<span data-ttu-id="8af46-462">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-462">Int16</span></span>|
|<span data-ttu-id="8af46-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="8af46-463">RADIX</span></span>|<span data-ttu-id="8af46-464">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-464">Int16</span></span>|
|<span data-ttu-id="8af46-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-465">NULLABLE</span></span>|<span data-ttu-id="8af46-466">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-466">Int16</span></span>|
|<span data-ttu-id="8af46-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-467">REMARKS</span></span>|<span data-ttu-id="8af46-468">String</span><span class="sxs-lookup"><span data-stu-id="8af46-468">String</span></span>|
|<span data-ttu-id="8af46-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-470">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="8af46-471">절차</span><span class="sxs-lookup"><span data-stu-id="8af46-471">Procedures</span></span>

|<span data-ttu-id="8af46-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-472">ColumnName</span></span>|<span data-ttu-id="8af46-473">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="8af46-475">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-475">String</span></span>|
|<span data-ttu-id="8af46-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af46-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="8af46-477">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-477">String</span></span>|
|<span data-ttu-id="8af46-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="8af46-479">String</span><span class="sxs-lookup"><span data-stu-id="8af46-479">String</span></span>|
|<span data-ttu-id="8af46-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8af46-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="8af46-481">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-481">Int16</span></span>|
|<span data-ttu-id="8af46-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8af46-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="8af46-483">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-483">Int16</span></span>|
|<span data-ttu-id="8af46-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="8af46-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="8af46-485">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-485">Int16</span></span>|
|<span data-ttu-id="8af46-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-486">REMARKS</span></span>|<span data-ttu-id="8af46-487">String</span><span class="sxs-lookup"><span data-stu-id="8af46-487">String</span></span>|
|<span data-ttu-id="8af46-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8af46-489">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="8af46-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8af46-490">ProcedureColumns</span></span>

|<span data-ttu-id="8af46-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-491">ColumnName</span></span>|<span data-ttu-id="8af46-492">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8af46-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="8af46-494">String</span><span class="sxs-lookup"><span data-stu-id="8af46-494">String</span></span>|
|<span data-ttu-id="8af46-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af46-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="8af46-496">String</span><span class="sxs-lookup"><span data-stu-id="8af46-496">String</span></span>|
|<span data-ttu-id="8af46-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="8af46-498">String</span><span class="sxs-lookup"><span data-stu-id="8af46-498">String</span></span>|
|<span data-ttu-id="8af46-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-499">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-500">String</span><span class="sxs-lookup"><span data-stu-id="8af46-500">String</span></span>|
|<span data-ttu-id="8af46-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-501">COLUMN_TYPE</span></span>|<span data-ttu-id="8af46-502">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-502">Int16</span></span>|
|<span data-ttu-id="8af46-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-503">DATA_TYPE</span></span>|<span data-ttu-id="8af46-504">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-504">Int16</span></span>|
|<span data-ttu-id="8af46-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-505">TYPE_NAME</span></span>|<span data-ttu-id="8af46-506">String</span><span class="sxs-lookup"><span data-stu-id="8af46-506">String</span></span>|
|<span data-ttu-id="8af46-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="8af46-507">PRECISION</span></span>|<span data-ttu-id="8af46-508">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-508">Int32</span></span>|
|<span data-ttu-id="8af46-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-509">LENGTH</span></span>|<span data-ttu-id="8af46-510">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-510">Int32</span></span>|
|<span data-ttu-id="8af46-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="8af46-511">SCALE</span></span>|<span data-ttu-id="8af46-512">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-512">Int16</span></span>|
|<span data-ttu-id="8af46-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="8af46-513">RADIX</span></span>|<span data-ttu-id="8af46-514">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-514">Int16</span></span>|
|<span data-ttu-id="8af46-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-515">NULLABLE</span></span>|<span data-ttu-id="8af46-516">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-516">Int16</span></span>|
|<span data-ttu-id="8af46-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-517">REMARKS</span></span>|<span data-ttu-id="8af46-518">String</span><span class="sxs-lookup"><span data-stu-id="8af46-518">String</span></span>|
|<span data-ttu-id="8af46-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="8af46-519">OVERLOAD</span></span>|<span data-ttu-id="8af46-520">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-520">Int32</span></span>|
|<span data-ttu-id="8af46-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-522">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="8af46-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8af46-523">ProcedureParameters</span></span>

|<span data-ttu-id="8af46-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="8af46-524">ColumnName</span></span>|<span data-ttu-id="8af46-525">DataType</span><span class="sxs-lookup"><span data-stu-id="8af46-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="8af46-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="8af46-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="8af46-527">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-527">String</span></span>|
|<span data-ttu-id="8af46-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8af46-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="8af46-529">String</span><span class="sxs-lookup"><span data-stu-id="8af46-529">String</span></span>|
|<span data-ttu-id="8af46-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="8af46-531">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-531">String</span></span>|
|<span data-ttu-id="8af46-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-532">COLUMN_NAME</span></span>|<span data-ttu-id="8af46-533">String</span><span class="sxs-lookup"><span data-stu-id="8af46-533">String</span></span>|
|<span data-ttu-id="8af46-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-534">COLUMN_TYPE</span></span>|<span data-ttu-id="8af46-535">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-535">Int16</span></span>|
|<span data-ttu-id="8af46-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-536">DATA_TYPE</span></span>|<span data-ttu-id="8af46-537">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-537">Int16</span></span>|
|<span data-ttu-id="8af46-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8af46-538">TYPE_NAME</span></span>|<span data-ttu-id="8af46-539">String</span><span class="sxs-lookup"><span data-stu-id="8af46-539">String</span></span>|
|<span data-ttu-id="8af46-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="8af46-540">COLUMN_SIZE</span></span>|<span data-ttu-id="8af46-541">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-541">Int32</span></span>|
|<span data-ttu-id="8af46-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="8af46-543">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-543">Int32</span></span>|
|<span data-ttu-id="8af46-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="8af46-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="8af46-545">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-545">Int16</span></span>|
|<span data-ttu-id="8af46-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="8af46-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="8af46-547">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-547">Int16</span></span>|
|<span data-ttu-id="8af46-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-548">NULLABLE</span></span>|<span data-ttu-id="8af46-549">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-549">Int16</span></span>|
|<span data-ttu-id="8af46-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8af46-550">REMARKS</span></span>|<span data-ttu-id="8af46-551">String</span><span class="sxs-lookup"><span data-stu-id="8af46-551">String</span></span>|
|<span data-ttu-id="8af46-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="8af46-552">COLUMN_DEF</span></span>|<span data-ttu-id="8af46-553">문자열</span><span class="sxs-lookup"><span data-stu-id="8af46-553">String</span></span>|
|<span data-ttu-id="8af46-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8af46-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="8af46-555">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-555">Int16</span></span>|
|<span data-ttu-id="8af46-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="8af46-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="8af46-557">Int16</span><span class="sxs-lookup"><span data-stu-id="8af46-557">Int16</span></span>|
|<span data-ttu-id="8af46-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8af46-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="8af46-559">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-559">Int32</span></span>|
|<span data-ttu-id="8af46-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8af46-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="8af46-561">Int32</span><span class="sxs-lookup"><span data-stu-id="8af46-561">Int32</span></span>|
|<span data-ttu-id="8af46-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8af46-562">IS_NULLABLE</span></span>|<span data-ttu-id="8af46-563">String</span><span class="sxs-lookup"><span data-stu-id="8af46-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="8af46-564">참고자료</span><span class="sxs-lookup"><span data-stu-id="8af46-564">See also</span></span>

- [<span data-ttu-id="8af46-565">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="8af46-565">ADO.NET Overview</span></span>](ado-net-overview.md)
