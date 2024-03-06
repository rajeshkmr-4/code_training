# code_training
require 'date'

def time_format(value)
 hours = (value / (60 * 60) ) % 60
 minutes = (value / 60 ) % 60
 seconds = value % 60
 "#{hours}h #{minutes}m #{seconds}s"
end


def fib(n)
  if (n == 1 || n == 2)
   return 1
  else
   return (fib(n-1)+fib(n-2))
  end
end

def multiplication_table(num)
puts "Enter the number:"
num=gets.chomp.to_i
i=2..10
while (i<=10)
	mult=num*i
	puts "#{num} * #{i} = #{mult}"mul_table(10)
	i+=1
 end
end

def postfix_to_infix(input)
	arr = input.split("")
	symbol_arr = []
	text_arr = []
	result = []
	arr.each do |el|
		((el == "+") || (el == "-") || (el == "*") || (el == "/") || (el == "%") ) ? symbol_arr << el : text_arr << el
	end
	a = 0
	b = symbol_arr.length - 1
	while (a <= text_arr.length)
		if (b >= 0)
			result << "#{text_arr[a]} #{symbol_arr[b]} #{text_arr[a+1]}"
			b = -1
		end
		a = +1
	end
	result
end


def for_mul_table(n)
	table = []
  for first_num in 2..n
  for second_num in 1..n
      table << first_num * second_num
    end
  end
  table
end

def while_multipication_table(input)
	multiplication_table = []
	first_num = 2
	while first_num <= input
		first_num += 1
		second_num = 1
		while second_num <= input
			multiplication_table << first_num*second_num
			puts multiplication_table
			second_num += 1
		end
	end
end

def compared_date(from, to)
	to_date = Date.today - last
	from_date = to_date - first
	diff = (to_date - from_date).to_i
	for_start = from_date.strftime('%Y-%m-%d')
	for_to = to_date.strftime('%Y-%m-%d')
	compared_date_start = from_date - diff
	comared_date_end = to_date - diff
	compared_date_start = compared_date_start.strftime('%Y-%m-%d')
	comared_date_end = comared_date_end.strftime('%Y-%m-%d')

	from_date = Date.parse(from)
	to_date = Date.parse(to)
	day_range = to_date - from_date
	{
		from: from_date - day_range,
		to: to_date - day_range
	}
end

def find_missing_num(array, act_start_value, actual_end_value)
	sorted_array = array.sort
	actual_value = act_start_value..actual_end_value
	actual_array = actual_value.to_a
	missing_num = actual_array - sorted_array
	retrun missing_num
end

def calculator(val_1, val_2, fun)
	if fun == '+'
		sum_value = val_1 + val_2
		return sum_value
	elsif
		fun == '-'
		sub_value = val_1 - val_2
		return sub_value
	elsif
		fun == '*'
		mul_value = val_1 * val_2
		return mul_value
	elsif
		fun == '/'
		div_value = val_1 / val_2
		return div_value
	end
end

def binary_search(n)
  value = 1..n/2
  array = value.to_a
  middle_value = array.length/2
  first_value = 0
  last_value = array.length - 1

  while first_value < last_value
    if middle_value**3 == n
      return middle_value
    elsif middle_value**3 < n
      first_value = middle_value
      middle_value = first_value + last_value / 2
    else
      last_value = middle_value
      middle_value = first_value + last_value / 2
    end
  end
  false
end
