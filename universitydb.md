# University DB

## Table name: `departments`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `name` (VARCHAR(255)) - NOT NULL

---

## Table name: `degree_courses`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `department_id` (BIGINT) - FK to `departments(id)` - NOT NULL
- `name` (VARCHAR(255)) - NOT NULL

---

## Table name: `courses`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `degree_course_id` (BIGINT) - FK to `degree_courses(id)` - NOT NULL
- `name` (VARCHAR(255)) - NOT NULL
- `description` (TEXT) - NULL

---

## Table name: `teachers`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `first_name` (VARCHAR(100)) - NOT NULL
- `last_name` (VARCHAR(100)) - NOT NULL
- `email` (VARCHAR(255)) - NOT NULL - UNIQUE

---

## Table name: `course_teachers`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `course_id` (BIGINT) - FK to `courses(id)` - NOT NULL
- `teacher_id` (BIGINT) - FK to `teachers(id)` - NOT NULL

---

## Table name: `exam_calls`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `course_id` (BIGINT) - FK to `courses(id)` - NOT NULL
- `exam_date` (DATE) - NOT NULL

---

## Table name: `students`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `first_name` (VARCHAR(100)) - NOT NULL
- `last_name` (VARCHAR(100)) - NOT NULL
- `email` (VARCHAR(255)) - NOT NULL - UNIQUE
- `degree_course_id` (BIGINT) - FK to `degree_courses(id)` - NOT NULL

---

## Table name: `exam_attendances`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `student_id` (BIGINT) - FK to `student(id)` - NOT NULL
- `exam_call_id` (BIGINT) - FK to `exam_calls(id)` - NOT NULL
- `grade` (DECIMAL(5,2)) - NULL

---

## Table name: `exam_attendance_Status`

**columns**:

- `id` (BIGINT) - primary key - auto_increment - NOT NULL
- `exam_attendance_id` (BIGINT) - FK to `exam_attendances(id)` - NOT NULL
- `status` (VARCHAR(50)) - NOT NULL
- `created_at` (TIMESTAMP) - NOT NULL
