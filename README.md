

AND Gate:
module and_gate(
	input wire a,
	input wire b,
	output wire y
);
assign y = a & b;
endmodule

OR Gate:
module or_gate(
	input wire a,
	input wire b,
	output wire y
);
assign y = a | b;
endmodule

 NOT Gate:
module not_gate(
	input wire a,
	output wire y
);
assign y = ~a;
endmodule

Half Adder:
module half_adder(
	input wire a,
	input wire b,
	output wire sum,
	output wire carry
);
assign sum = a ^ b;
assign carry = a & b;
endmodule

Full Adder:
module full_adder(
	input wire a,
	input wire b,
	input wire cin,
	output wire sum,
	output wire cout
);
assign sum = a ^ b ^ cin;
assign cout = (a & b) | (a & cin) | (b & cin);
endmodule

2-to-1 Multiplexer:
module mux2to1(
	input wire a,
	input wire b,
	input wire sel,
	output wire y
);
assign y = sel ? b : a;
endmodule

TEST BENCH CODE:
module testbench;
reg a, b, sel;
wire y;
mux2to1 mux(a, b, sel, y);
initial begin
	a = 0; b = 0; sel = 0; #10
	a = 0; b = 1; sel = 0; #10
	a = 1; b = 0; sel = 0; #10
	a = 1; b = 1; sel = 0; #10
	a = 0; b = 0; sel = 1; #10
	a = 0; b = 1; sel = 1; #10
	a = 1; b = 0; sel = 1; #10
	a = 1; b = 1; sel = 1; #10
end
endmodule
